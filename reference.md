# Reference
## Chat
<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">list_chat_completions</a>(...) -> ListChatCompletionsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of chat completions (prompts) for the agent, with applied tags expanded as { id, name } and share metadata.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.list_chat_completions()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**per_page:** `typing.Optional[int]` — Results per page (clamped to 100).
    
</dd>
</dl>

<dl>
<dd>

**agent_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**channel_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**bible_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**cached:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**client:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**config_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**conversation_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**device_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**flagged:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**favorited:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**language:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**liked:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**session_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">create_chat_completion</a>(...) -> ChatCompletionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a chat completion using the agent's configured model. Supports both streaming and non-streaming responses.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.create_chat_completion(
    request={"key": "value"},
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `ChatCompletionRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">like_completion</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the like status of a specific chat completion
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.like_completion(
    id="id",
    liked=True,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the chat completion
    
</dd>
</dl>

<dl>
<dd>

**liked:** `bool` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">flag_completion</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the flagged status of a specific chat completion
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.flag_completion(
    id="id",
    flagged=True,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the chat completion
    
</dd>
</dl>

<dl>
<dd>

**flagged:** `bool` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">feedback_completion</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Adds user feedback to a specific chat completion
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.feedback_completion(
    id="id",
    feedback="feedback",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the chat completion
    
</dd>
</dl>

<dl>
<dd>

**feedback:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">share_completion</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a share record for a specific chat completion
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.share_completion(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the chat completion
    
</dd>
</dl>

<dl>
<dd>

**conversation_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**session_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.chat.<a href="src/apologist/chat/client.py">get_chat_completion</a>(...) -> GetChatCompletionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single chat completion (prompt) by numeric id or UUID, including applied tags, guardrail/cta metadata, share metadata, and automation results.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.chat.get_chat_completion(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The numeric id or UUID of the chat completion
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Corpus
<details><summary><code>client.corpus.<a href="src/apologist/corpus/client.py">search_corpus</a>(...) -> SearchCorpusResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Performs a semantic search across the agent's corpus of knowledge
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.corpus.search_corpus(
    query="query",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**query:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[CorpusSearchRequestFilters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.corpus.<a href="src/apologist/corpus/client.py">log_corpus_view</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Records that a user viewed a specific corpus item
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.corpus.log_corpus_view(
    model="model",
    id="id",
    prompt_id="prompt_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model:** `str` — The model type (e.g., 'source')
    
</dd>
</dl>

<dl>
<dd>

**id:** `str` — The ID of the corpus item
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.corpus.<a href="src/apologist/corpus/client.py">log_corpus_impression</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Records that a corpus item was shown to a user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.corpus.log_corpus_impression(
    model="model",
    id="id",
    prompt_id="prompt_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model:** `str` — The model type (e.g., 'source')
    
</dd>
</dl>

<dl>
<dd>

**id:** `str` — The ID of the corpus item
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.corpus.<a href="src/apologist/corpus/client.py">log_corpus_referral_redirect</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Records a referral for a corpus item and, when a `url` is supplied, issues a 302 redirect to it. Without a `url`, responds with a success message. Requires either the search API entitlement or a same-origin request.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.corpus.log_corpus_referral_redirect(
    model="model",
    id="id",
    prompt_id="prompt_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model:** `str` — The model type (e.g., 'source')
    
</dd>
</dl>

<dl>
<dd>

**id:** `str` — The numeric ID of the corpus item
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**url:** `typing.Optional[str]` — URL-encoded destination to redirect to after logging the referral.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.corpus.<a href="src/apologist/corpus/client.py">log_corpus_referral</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Records that a user was referred to a corpus item
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.corpus.log_corpus_referral(
    model="model",
    id="id",
    prompt_id="prompt_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model:** `str` — The model type (e.g., 'source')
    
</dd>
</dl>

<dl>
<dd>

**id:** `str` — The ID of the corpus item
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Evaluators
<details><summary><code>client.evaluators.<a href="src/apologist/evaluators/client.py">list_evaluations</a>(...) -> ListEvaluationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of evaluations for the evaluator, scoped to the requesting agent.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.evaluators.list_evaluations(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID or key of the evaluator
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**per_page:** `typing.Optional[int]` — Results per page (clamped to 100).
    
</dd>
</dl>

<dl>
<dd>

**min_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_duration:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_duration:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_score:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_score:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**passed:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**benchmark:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**benchmark_run_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**benchmark_question_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/apologist/evaluators/client.py">evaluate_content</a>(...) -> EvaluateContentResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Runs an evaluation on the provided content using the specified evaluator
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.evaluators.evaluate_content(
    id="id",
    content="content",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID or key of the evaluator
    
</dd>
</dl>

<dl>
<dd>

**content:** `EvaluatorRequestContent` 
    
</dd>
</dl>

<dl>
<dd>

**frequency_penalty:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**confidence_threshold:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**model:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**presence_penalty:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**reasoning_effort:** `typing.Optional[EvaluatorRequestReasoningEffort]` 
    
</dd>
</dl>

<dl>
<dd>

**verbosity:** `typing.Optional[EvaluatorRequestVerbosity]` 
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**top_p:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**variables:** `typing.Optional[typing.Dict[str, typing.Optional[str]]]` — Flat string key/value pairs substituted into `{key}` placeholders in the evaluator prompt. Reserved keys (`options`, `option_descriptions`, `criteria`) cannot be overridden. Not persisted; omitted from the response.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/apologist/evaluators/client.py">get_evaluation</a>(...) -> GetEvaluationResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single evaluation for the evaluator, scoped to the requesting agent.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.evaluators.get_evaluation(
    id="id",
    evaluation_id="evaluationId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The id or key of the evaluator
    
</dd>
</dl>

<dl>
<dd>

**evaluation_id:** `str` — The id or UUID of the evaluation
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## CTAs
<details><summary><code>client.ct_as.<a href="src/apologist/ct_as/client.py">match_ctas</a>(...) -> MatchCtasResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Finds matching CTAs based on conversation context, user, session, device, or messages
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.ct_as.match_ctas(
    request={"key": "value"},
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CtaMatchRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ct_as.<a href="src/apologist/ct_as/client.py">log_cta_click</a>(...) -> SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Records that a user clicked on a specific CTA
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.ct_as.log_cta_click(
    id="id",
    prompt_id="prompt_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the CTA
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Users
<details><summary><code>client.users.<a href="src/apologist/users/client.py">list_users</a>(...) -> ListUsersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of users for the agent's team, with applied tags expanded as { id, name } and the persisted responder id.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.users.list_users()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**per_page:** `typing.Optional[int]` — Results per page (clamped to 100).
    
</dd>
</dl>

<dl>
<dd>

**external_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.Optional[str]` — Comma-separated tag ids.
    
</dd>
</dl>

<dl>
<dd>

**responder_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.users.<a href="src/apologist/users/client.py">list_user_flags</a>(...) -> ListUserFlagsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of user flag definitions for the agent's team (all columns from user_flags), ordered by id ascending.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.users.list_user_flags()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**per_page:** `typing.Optional[int]` — Results per page (clamped to 100).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.users.<a href="src/apologist/users/client.py">get_user</a>(...) -> GetUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single user by external id or internal id, with expanded tags and the persisted responder for the agent.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.users.get_user(
    user_id="user_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_id:** `str` — The user's external id or internal id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.users.<a href="src/apologist/users/client.py">update_user</a>(...) -> UpdateUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates a user's external_id and/or tags and upserts the persisted responder for the agent. Only provided fields are changed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.users.update_user(
    user_id="user_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_id:** `str` — The user's external id or internal id
    
</dd>
</dl>

<dl>
<dd>

**external_id:** `typing.Optional[str]` — Your external identifier for the user.
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.Optional[typing.List[UserUpdateRequestTagsItem]]` — Applied tags as a mix of existing tag ids and/or default-language tag names. Unknown ids or names are rejected. Tags are mirror-owned and never created here.
    
</dd>
</dl>

<dl>
<dd>

**responder_id:** `typing.Optional[int]` — Responder to persist for this user on the requesting agent. Must be active on the agent.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Benchmarks
<details><summary><code>client.benchmarks.<a href="src/apologist/benchmarks/client.py">list_benchmark_runs</a>(...) -> ListBenchmarkRunsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of runs for a benchmark, scoped to the requesting agent. Each run carries nested evaluators, questions, and a flat evaluations array.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.benchmarks.list_benchmark_runs(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The id or key of the benchmark
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**per_page:** `typing.Optional[int]` — Results per page (clamped to 100).
    
</dd>
</dl>

<dl>
<dd>

**min_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_timestamp:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_duration:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_duration:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_score:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_score:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**passed:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**min_responses:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**max_responses:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.benchmarks.<a href="src/apologist/benchmarks/client.py">run_benchmark</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Executes a benchmark run and returns the aggregated result with nested evaluators, questions, and a flat evaluations array.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.benchmarks.run_benchmark(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The id or key of the benchmark
    
</dd>
</dl>

<dl>
<dd>

**content:** `typing.Optional[BenchmarkRunRequestContent]` — Content to evaluate. Required when `source_id` is supplied.
    
</dd>
</dl>

<dl>
<dd>

**completion_id:** `typing.Optional[str]` — Completion UUID whose stored response should be evaluated.
    
</dd>
</dl>

<dl>
<dd>

**source_id:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**model:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**num_responses:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**use_question_variants:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**reasoning_effort:** `typing.Optional[BenchmarkRunRequestReasoningEffort]` 
    
</dd>
</dl>

<dl>
<dd>

**verbosity:** `typing.Optional[BenchmarkRunRequestVerbosity]` 
    
</dd>
</dl>

<dl>
<dd>

**score_threshold:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**value_threshold:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**top_p:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**frequency_penalty:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**presence_penalty:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.benchmarks.<a href="src/apologist/benchmarks/client.py">get_benchmark_run</a>(...) -> GetBenchmarkRunResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single benchmark run by id or UUID, scoped to the requesting agent, including nested evaluators, questions, and evaluations.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.benchmarks.get_benchmark_run(
    id="id",
    run_id="runId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The id or key of the benchmark
    
</dd>
</dl>

<dl>
<dd>

**run_id:** `str` — The id or UUID of the run
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Channels
<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">get_discord_channel_status</a>(...) -> GetDiscordChannelStatusResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the status of the Discord channel. Used as a lightweight health/verification endpoint.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.get_discord_channel_status(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">receive_discord_interaction</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Receives Discord interaction callbacks for the channel. Requests are verified via Ed25519 signature headers; unsigned or invalid requests are rejected. Payload shape is defined by Discord.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.receive_discord_interaction(
    id="id",
    signature_ed25519="x-signature-ed25519",
    signature_timestamp="x-signature-timestamp",
    request={
        "key": "value"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**signature_ed25519:** `str` — Discord request signature (hex).
    
</dd>
</dl>

<dl>
<dd>

**signature_timestamp:** `str` — Discord request timestamp.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Dict[str, typing.Any]` — Discord interaction payload.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">verify_facebook_webhook</a>(...) -> str</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the Meta webhook verification handshake, echoing `hub.challenge` when `hub.verify_token` matches the channel's configured token.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.verify_facebook_webhook(
    id="id",
    hub_mode="subscribe",
    hub_verify_token="hub.verify_token",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**hub_mode:** `VerifyFacebookWebhookRequestHubMode` 
    
</dd>
</dl>

<dl>
<dd>

**hub_verify_token:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**hub_challenge:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">receive_facebook_message</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Receives Facebook/Messenger (and Instagram-style) message events for the channel. Payload shape is defined by Meta.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.receive_facebook_message(
    id="id",
    request={
        "key": "value"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Dict[str, typing.Any]` — Meta webhook payload.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">get_instagram_privacy_policy</a>(...) -> str</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a static HTML privacy policy page for the Instagram integration.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.get_instagram_privacy_policy(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">receive_telegram_update</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Receives Telegram bot update events for the channel. Non-message updates are acknowledged and ignored. Payload shape is defined by Telegram.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.receive_telegram_update(
    id="id",
    request={
        "key": "value"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Dict[str, typing.Any]` — Telegram update payload.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.channels.<a href="src/apologist/channels/client.py">receive_twilio_message</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Receives inbound Twilio messages for the channel as form-encoded data. Payload fields are defined by Twilio.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.channels.receive_twilio_message(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The channel id
    
</dd>
</dl>

<dl>
<dd>

**from:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**body:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Shares
<details><summary><code>client.shares.<a href="src/apologist/shares/client.py">get_shared_messages</a>(...) -> GetSharedMessagesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Public, unauthenticated read of the messages behind a share token. The token is the bearer capability and enforces tenant isolation against the host agent. An empty or invalid token yields an empty messages array.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from apologist import ApologistAgent
from apologist.environment import ApologistAgentEnvironment

client = ApologistAgent(
    api_key="<value>",
    environment=ApologistAgentEnvironment.DEFAULT,
)

client.shares.get_shared_messages(
    token="token",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**token:** `str` — The share token
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

