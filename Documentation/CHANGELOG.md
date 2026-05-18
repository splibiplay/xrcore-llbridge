# Changelog

## 0.1.1

- Repositioned module as **XRCore LLM Bridge** (commercial naming).
- Clarified architecture boundaries: not an agent, no training logic, no MCP dependency.
- Added AI capability surface:
  - `llm.generate_response`
  - `llm.route_prompt`
  - `llm.summarize_context`
  - `llm.execute_tool_call`
  - `llm.normalize_response`
- Added explicit runtime layers:
  - Providers
  - Conversations
  - PromptRouting
  - ToolCalling
  - EventBridge
  - AnalyticsTraces
- Added orchestration traces (route/tool-call/summary/normalization).

## 0.1.0

- Initial LLBridge module baseline.
