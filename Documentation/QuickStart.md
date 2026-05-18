# XRCore LLM Bridge QuickStart

## Goal

Validate prompt routing, tool-call planning, normalized responses, and context traces in under two minutes.

## Steps

1. Install `XRCore SDK`, `XRCore Context`, `XRCore Voice`, and `XRCore LLM Bridge`.
2. Add `XRLLBridgeRuntime` to a scene object.
3. Assign an `XRLLBridgeProfile`.
4. Call `EmitBridgeSignal("status")` (or any prompt).

## Expected Runtime Signals

- `xr.llbridge.prompt.submitted`
- `xr.llbridge.prompt.routed`
- `xr.llbridge.tool_call.planned` (when route triggers tool intent)
- `xr.llbridge.response.normalized`
- `xr.llbridge.response.generated`

## Expected Context Keys

- `llbridge.lastPrompt`
- `llbridge.lastRoute`
- `llbridge.lastToolCall`
- `llbridge.lastSummary`
- `llbridge.lastNormalizedResponse`
- `llbridge.lastResponse`

## Optional AI Integration

When `com.xrcore.ai` is present, the bridge registers:

- `llm.generate_response`
- `llm.route_prompt`
- `llm.summarize_context`
- `llm.execute_tool_call`
- `llm.normalize_response`
