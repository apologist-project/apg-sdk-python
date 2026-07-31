# Apologist Python SDK

Official Python client for the [Apologist Agent API](https://docs.apologist.ai).

## Install

```bash
pip install apologist
```

## Quickstart

```python
import os
from apologist import ApologistAgentClient

client = ApologistAgentClient(
    domain="YOUR_AGENT_HOST",
    api_key=os.environ["APOLOGIST_API_KEY"],
)
```

## Documentation

- Product docs: https://docs.apologist.ai
- API reference: https://docs.apologist.ai/agent-api/api-reference
- Source: https://github.com/apologist-project/apg-sdk-python

## License

See the repository for license details.
