# ApologistAi Python Library

[![fern shield](https://img.shields.io/badge/%F0%9F%8C%BF-Built%20with%20Fern-brightgreen)](https://buildwithfern.com?utm_source=github&utm_medium=github&utm_campaign=readme&utm_source=https%3A%2F%2Fgithub.com%2Fapologist-project%2Fapg-sdk-python)
[![pypi](https://img.shields.io/pypi/v/apologist)](https://pypi.python.org/pypi/apologist)

The ApologistAi Python library provides convenient access to the ApologistAi APIs from Python.

## Table of Contents

- [Documentation](#documentation)
- [Installation](#installation)
- [Reference](#reference)
- [Usage](#usage)
- [Async Usage](#async-usage)
- [Using Types](#using-types)
- [Nested Params](#nested-params)
- [Handling Errors](#handling-errors)
- [Environments](#environments)
- [Async Client](#async-client)
- [Exception Handling](#exception-handling)
- [Advanced](#advanced)
  - [Access Raw Response Data](#access-raw-response-data)
  - [Retries](#retries)
  - [Timeouts](#timeouts)
  - [Custom Client](#custom-client)
- [Versioning](#versioning)
- [Requirements](#requirements)
- [Contributing](#contributing)

## Documentation

The full API of this library can be found in [api.md](api.md).

## Installation

```sh
pip install apologist
```

## Reference

A full reference for this library is available [here](https://github.com/apologist-project/apg-sdk-python/blob/HEAD/./reference.md).

## Usage

Instantiate and use the client with the following:

```python
from apologist import ApologistAgent

client = ApologistAgent(
    api_key="<value>",
)

client.chat.create_chat_completion(
    request={"key": "value"},
)
```

## Async usage

Simply import `AsyncApologist` instead of `Apologist` and use `await` with each API call:

```python
import os
import asyncio
from apologist import AsyncApologist

client = AsyncApologist(
    api_key=os.environ.get("APOLOGIST_API_KEY"),  # This is the default and can be omitted
)


async def main() -> None:
    pet = await client.pet.update(
        name="doggie",
        photo_urls=["string"],
    )
    print(pet.id)


asyncio.run(main())
```

Functionality between the synchronous and asynchronous clients is otherwise identical.

### With aiohttp

By default, the async client uses `httpx` for HTTP requests. However, for improved concurrency performance you may also use `aiohttp` as the HTTP backend.

You can enable this by installing `aiohttp`:

```sh
# install from PyPI
pip install apologist[aiohttp]
```

Then you can enable it by instantiating the client with `http_client=DefaultAioHttpClient()`:

```python
import os
import asyncio
from apologist import DefaultAioHttpClient
from apologist import AsyncApologist


async def main() -> None:
    async with AsyncApologist(
        api_key=os.environ.get("APOLOGIST_API_KEY"),  # This is the default and can be omitted
        http_client=DefaultAioHttpClient(),
    ) as client:
        pet = await client.pet.update(
            name="doggie",
            photo_urls=["string"],
        )
        print(pet.id)


asyncio.run(main())
```

## Using types

Nested request parameters are [TypedDicts](https://docs.python.org/3/library/typing.html#typing.TypedDict). Responses are [Pydantic models](https://docs.pydantic.dev) which also provide helper methods for things like:

- Serializing back into JSON, `model.to_json()`
- Converting to a dictionary, `model.to_dict()`

Typed requests and responses provide autocomplete and documentation within your editor. If you would like to see type errors in VS Code to help catch bugs earlier, set `python.analysis.typeCheckingMode` to `basic`.

## Nested params

Nested parameters are dictionaries, typed using `TypedDict`, for example:

```python
from apologist import Apologist

client = Apologist()

pet = client.pet.update(
    name="doggie",
    photo_urls=["string"],
    category={},
)
print(pet.category)
```

## Handling errors

When the library is unable to connect to the API (for example, due to network connection problems or a timeout), a subclass of `apologist.APIConnectionError` is raised.

When the API returns a non-success status code (that is, 4xx or 5xx
response), a subclass of `apologist.APIStatusError` is raised, containing `status_code` and `response` properties.

All errors inherit from `apologist.APIError`.

```python
import apologist
from apologist import Apologist

client = Apologist()

try:
    client.pet.update(
        name="doggie",
        photo_urls=["string"],
    )
except apologist.APIConnectionError as e:
    print("The server could not be reached")
    print(e.__cause__)  # an underlying Exception, likely raised within httpx.
except apologist.RateLimitError as e:
    print("A 429 status code was received; we should back off a bit.")
except apologist.APIStatusError as e:
    print("Another non-200-range status code was received")
    print(e.status_code)
    print(e.response)
```

Error codes are as follows:

| Status Code | Error Type                 |
| ----------- | -------------------------- |
| 400         | `BadRequestError`          |
| 401         | `AuthenticationError`      |
| 403         | `PermissionDeniedError`    |
| 404         | `NotFoundError`            |
| 422         | `UnprocessableEntityError` |
| 429         | `RateLimitError`           |
| >=500       | `InternalServerError`      |
| N/A         | `APIConnectionError`       |

### Retries

Certain errors are automatically retried 2 times by default, with a short exponential backoff.
Connection errors (for example, due to a network connectivity problem), 408 Request Timeout, 409 Conflict,
429 Rate Limit, and >=500 Internal errors are all retried by default.

You can use the `max_retries` option to configure or disable retry settings:

```python
from apologist import Apologist

# Configure the default for all requests:
client = Apologist(
    # default is 2
    max_retries=0,
)

# Or, configure per-request:
client.with_options(max_retries=5).pet.update(
    name="doggie",
    photo_urls=["string"],
)
```

### Timeouts

By default requests time out after 1 minute. You can configure this with a `timeout` option,
which accepts a float or an [`httpx.Timeout`](https://www.python-httpx.org/advanced/timeouts/#fine-tuning-the-configuration) object:

```python
from apologist import Apologist

# Configure the default for all requests:
client = Apologist(
    # 20 seconds (default is 1 minute)
    timeout=20.0,
)

# More granular control:
client = Apologist(
    timeout=httpx.Timeout(60.0, read=5.0, write=10.0, connect=2.0),
)

# Override per-request:
client.with_options(timeout=5.0).pet.update(
    name="doggie",
    photo_urls=["string"],
)
```

On timeout, an `APITimeoutError` is thrown.

Note that requests that time out are [retried twice by default](#retries).

## Environments

This SDK allows you to configure different environments for API requests.

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    environment=ApologistAgentEnvironment.DEFAULT,
)
```

## Async Client

The SDK also exports an `async` client so that you can make non-blocking calls to our API. Note that if you are constructing an Async httpx client class to pass into this client, use `httpx.AsyncClient()` instead of `httpx.Client()` (e.g. for the `httpx_client` parameter of this client).

```python
import asyncio

from apologist import AsyncApologistAgent

client = AsyncApologistAgent(
    api_key="<value>",
)


async def main() -> None:
    await client.chat.create_chat_completion(
        request={"key": "value"},
    )


asyncio.run(main())
```

## Exception Handling

When the API returns a non-success status code (4xx or 5xx response), a subclass of the following error
will be thrown.

```python
from apologist.core.api_error import ApiError

try:
    client.chat.create_chat_completion(...)
except ApiError as e:
    print(e.status_code)
    print(e.body)
```

## Advanced

### Access Raw Response Data

The SDK provides access to raw response data, including headers, through the `.with_raw_response` property.
The `.with_raw_response` property returns a "raw" client that can be used to access the `.headers` and `.data` attributes.

```python
from apologist import ApologistAgent

client = ApologistAgent(...)
response = client.chat.with_raw_response.create_chat_completion(...)
print(response.headers)  # access the response headers
print(response.status_code)  # access the response status code
print(response.data)  # access the underlying object
```

### Retries

The SDK is instrumented with automatic retries with exponential backoff. A request will be retried as long
as the request is deemed retryable and the number of retry attempts has not grown larger than the configured
retry limit (default: 2).

Which status codes are retried depends on the `retryStatusCodes` generator configuration:

**`legacy`** (current default): retries on
- [408](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/408) (Timeout)
- [409](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/409) (Conflict)
- [429](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429) (Too Many Requests)
- [5XX](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#server_error_responses) (All server errors, including 500)

**`recommended`**: retries on
- [408](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/408) (Timeout)
- [409](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/409) (Conflict)
- [429](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429) (Too Many Requests)
- [502](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/502) (Bad Gateway)
- [503](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/503) (Service Unavailable)
- [504](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/504) (Gateway Timeout)

Use the `max_retries` request option to configure this behavior.

```python
client.chat.create_chat_completion(..., request_options={
    "max_retries": 1
})
```

### Timeouts

The SDK defaults to a 60 second timeout. You can configure this with a timeout option at the client or request level.

```python
from apologist import ApologistAgent

client = ApologistAgent(..., timeout=20.0)

# Override timeout for a specific method
client.chat.create_chat_completion(..., request_options={
    "timeout": 1
})
```

### Custom Client

You can override the `httpx` client to customize it for your use-case. Some common use-cases include support for proxies
and transports.

```python
import httpx
from apologist import ApologistAgent

client = ApologistAgent(
    ...,
    httpx_client=httpx.Client(
        proxy="http://my.test.proxy.example.com",
        transport=httpx.HTTPTransport(local_address="0.0.0.0"),
    ),
)
```

## Versioning

This package generally follows [SemVer](https://semver.org/spec/v2.0.0.html) conventions, though certain backwards-incompatible changes may be released as minor versions:

1. Changes that only affect static types, without breaking runtime behavior.
2. Changes to library internals which are technically public but not intended or documented for external use. _(Please open a GitHub issue to let us know if you are relying on such internals.)_
3. Changes that we do not expect to impact the vast majority of users in practice.

We take backwards-compatibility seriously and work hard to ensure you can rely on a smooth upgrade experience.

We are keen for your feedback; please open an [issue](https://www.github.com/apologist-project/apg-sdk-python/issues) with questions, bugs, or suggestions.

### Determining the installed version

If you've upgraded to the latest version but aren't seeing any new features you were expecting then your python environment is likely still using an older version.

You can determine the version that is being used at runtime with:

```py
import apologist
print(apologist.__version__)
```

## Requirements

Python 3.9 or higher.

## Contributing

While we value open-source contributions to this SDK, this library is generated programmatically.
Additions made directly to this library would have to be moved over to our generation code,
otherwise they would be overwritten upon the next generated release. Feel free to open a PR as
a proof of concept, but know that we will not be able to merge it as-is. We suggest opening
an issue first to discuss with us!

On the other hand, contributions to the README are always very welcome!
