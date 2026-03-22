# Does GitHub Copilot CLI telemetry offer insight into plan mode usage?

Yes, but only partially.

GitHub’s usage metrics dashboard and APIs **do expose plan-mode usage for Copilot Chat in the IDE**. The official metrics reference lists **Requests per chat mode** and **Model usage per chat mode**, with chat modes broken out as **Ask, Edit, Plan, and Agent**. citeturn440424search0turn440424search5

However, GitHub’s documented metrics for **Copilot CLI** are much more coarse. The usage-metrics reference includes CLI-oriented fields such as:
- `daily_active_cli_users`
- `session_count`
- `request_count`
- `prompt_count`
- CLI token usage
- last known CLI version

Those fields help you understand **overall CLI usage**, but they do **not** provide a documented first-class metric specifically for **CLI plan mode usage**. citeturn440424search0turn440424search3

There is an important distinction here: GitHub’s premium request documentation says that **plan mode is included in Copilot Chat in an IDE**, while **Copilot CLI** is counted separately as its own request source. That supports the conclusion that the built-in “chat mode” breakdown is about IDE chat activity, not CLI activity. citeturn440424search8turn440424search5

That said, there is still a useful workaround. GitHub documents that **Copilot CLI can export traces and metrics via OpenTelemetry (OTel)**, including visibility into:
- agent interactions
- LLM calls
- tool executions
- token usage

This means you can likely **derive** plan-mode usage yourself if you control the CLI environment and collect OTel signals. For example, you may be able to detect sessions that invoke plan-oriented flows or commands and classify those as planning sessions in your own telemetry pipeline. citeturn440424search1

So the practical answer is:

- **IDE Copilot Chat:** yes, built-in plan-mode telemetry exists. citeturn440424search0turn440424search5
- **Copilot CLI:** no documented built-in plan-mode metric appears in the usage metrics API. citeturn440424search0turn440424search3
- **Workaround:** use CLI OTel traces and derive plan-like session behavior yourself. citeturn440424search1

## Recommended derived metrics

If your goal is to understand whether developers are using the CLI in a planning-oriented way, these derived metrics would be useful:

### 1. CLI plan engagement rate
`Sessions containing plan-oriented interactions ÷ total CLI sessions`

### 2. CLI plan-to-execution conversion
`Sessions with plan-oriented interactions that later execute tools or edits ÷ sessions with plan-oriented interactions`

### 3. CLI multi-step reasoning rate
`CLI sessions with more than N tool calls or reasoning steps ÷ total CLI sessions`

### 4. CLI planning persistence
`Average number of turns in planning-oriented CLI sessions`

### 5. CLI plan reuse rate
`Users with repeated planning-oriented CLI sessions across weeks ÷ CLI active users`

## Bottom line

If you are looking for a **native GitHub Copilot metric** for **CLI plan mode usage**, I do not see one in the documented usage metrics. But if you can collect **OpenTelemetry from Copilot CLI**, you should be able to build a strong proxy metric that is probably more useful anyway, because it can reflect actual planning behavior rather than only a UI mode label. citeturn440424search0turn440424search1turn440424search8
