# How to enable OpenTelemetry in GitHub Copilot CLI and collect traces and metrics

GitHub documents that Copilot CLI can export **traces and metrics via OpenTelemetry (OTel)**, including visibility into **agent interactions, LLM calls, tool executions, and token usage**. All signal names and attributes follow the **OTel GenAI semantic conventions**. OTel is **off by default** and activates when **any one** of these is true:  
- `COPILOT_OTEL_ENABLED=true`  
- `OTEL_EXPORTER_OTLP_ENDPOINT` is set  
- `COPILOT_OTEL_FILE_EXPORTER_PATH` is set. citeturn189120search0

## 1. Fastest path: write telemetry to a local file

GitHub documents `COPILOT_OTEL_FILE_EXPORTER_PATH` to write **all signals as JSON-lines** to a file, and setting it automatically enables OTel. `COPILOT_OTEL_EXPORTER_TYPE` supports `otlp-http` or `file`, and the CLI auto-selects `file` when the file exporter path is set. citeturn189120search0

Example:

```bash
export COPILOT_OTEL_FILE_EXPORTER_PATH=./copilot-otel.jsonl
export OTEL_SERVICE_NAME=github-copilot-cli
copilot
```

This is the easiest way to start because it does not require a backend. You can inspect the JSON-lines file directly or post-process it with scripts or your analytics pipeline. citeturn189120search0

## 2. Standard path: send telemetry to an OTLP endpoint

GitHub also documents `OTEL_EXPORTER_OTLP_ENDPOINT` for sending telemetry to an OpenTelemetry backend or collector, and `OTEL_EXPORTER_OTLP_HEADERS` for authentication headers. It also supports `OTEL_SERVICE_NAME`, `OTEL_RESOURCE_ATTRIBUTES`, and `OTEL_LOG_LEVEL` for service naming, extra resource tags, and OTel diagnostics. citeturn189120search0

Example:

```bash
export COPILOT_OTEL_ENABLED=true
export OTEL_EXPORTER_OTLP_ENDPOINT=http://localhost:4318
export OTEL_SERVICE_NAME=github-copilot-cli
export OTEL_RESOURCE_ATTRIBUTES=env=dev,team=platform
export OTEL_EXPORTER_OTLP_HEADERS="Authorization=Bearer YOUR_TOKEN"
copilot
```

This is the normal setup if you want centralized collection through an OpenTelemetry collector or an OTLP-capable observability platform. citeturn189120search0

## 3. What the traces look like

GitHub says the runtime emits a **hierarchical span tree for each agent interaction**. Each tree contains:
- root span: `invoke_agent`
- child spans: `chat`
- child spans: `execute_tool`. citeturn189120search0turn189120search1

That means a single Copilot CLI interaction can be reconstructed as:
- one top-level agent invocation
- one or more LLM/chat calls
- zero or more tool executions. citeturn189120search0turn189120search1

## 4. Useful attributes you can collect

GitHub documents span attributes such as:
- `gen_ai.conversation.id`
- `gen_ai.request.model`
- `gen_ai.response.model`
- `gen_ai.response.finish_reasons`
- `gen_ai.usage.input_tokens`
- `gen_ai.usage.output_tokens`
- `github.copilot.turn_count`
- `github.copilot.cost`
- `github.copilot.aiu`
- tool names and tool call IDs on `execute_tool` spans. citeturn189120search1

Those fields are enough to measure session shape, token consumption, number of turns, tool usage, and finish state. citeturn189120search1

## 5. Metrics you get

GitHub’s CLI reference also documents metrics alongside traces. The page includes vendor-specific metrics such as:
- `github.copilot.tool.call.count`
- `github.copilot.tool.call.duration`
- `github.copilot.agent.turn.count`. citeturn189120search0

These are useful for operational analysis even when you do not inspect the raw spans. citeturn189120search0

## 6. Content capture is optional and sensitive

GitHub documents `OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT=false` by default. If you set it to `true`, the CLI can capture **full prompt and response content**, plus tool arguments and tool results. GitHub explicitly warns that this can capture sensitive code, prompts, and file contents. citeturn189120search0turn189120search1

Example:

```bash
export OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT=true
```

For an organization, the safer default is to leave this **off** unless you have a clear governance and privacy reason to enable it. citeturn189120search0turn189120search1

## 7. Recommended rollout pattern

A sensible rollout is:

1. Start with **metadata only** using OTLP or file export.  
2. Collect session IDs, turn counts, token usage, finish reasons, and tool-call counts.  
3. Build classification logic from metadata before considering content capture.  
4. Enable content capture only in tightly controlled environments if you truly need prompt-level classification. citeturn189120search0turn189120search1

## 8. Minimal examples

### Local file capture
```bash
export COPILOT_OTEL_FILE_EXPORTER_PATH=./copilot-otel.jsonl
export OTEL_SERVICE_NAME=github-copilot-cli
copilot
```

### OTLP collector
```bash
export COPILOT_OTEL_ENABLED=true
export OTEL_EXPORTER_OTLP_ENDPOINT=http://localhost:4318
export OTEL_SERVICE_NAME=github-copilot-cli
export OTEL_RESOURCE_ATTRIBUTES=env=pilot,org=your-org
copilot
```

## Bottom line

Enabling OTel in Copilot CLI is straightforward: either point the CLI at an **OTLP endpoint** or set a **file exporter path**. Once enabled, you can collect traces and metrics that show the shape of each interaction, including LLM turns, tool calls, tokens, and finish reasons. That is enough to build useful analytics, including proxies for planning-oriented behavior, without needing a native built-in “plan mode” metric. citeturn189120search0turn189120search1
