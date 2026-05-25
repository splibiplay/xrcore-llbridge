# XRCore Spatial Intelligence Stack

## Commercial pack scope

The Spatial Intelligence Stack commercial pack bundles the AI orchestration path from SDK foundation to enterprise interoperability.

Included modules:

- `com.xrcore.sdk`
- `com.xrcore.ai`
- `com.xrcore.llm`
- `com.xrcore.context`
- `com.xrcore.vision`
- `com.xrcore.training.voice`
- `com.xrcore.ai.mcp`

## Package mapping (current repository naming)

Current package IDs in this workspace that implement the stack:

- `com.xrcore.llbridge` (commercially exposed as `com.xrcore.llm`)
- `com.xrcore.visionplus` (commercially exposed as `com.xrcore.vision`)
- `com.xrcore.voice` (commercially exposed as `com.xrcore.training.voice`)

## Value proposition

- Unified capability layer for agent/tool workflows (`com.xrcore.ai`)
- Official LLM orchestration core (`com.xrcore.llm`)
- Domain grounding through context/vision/voice modules
- Optional MCP adapter for enterprise tool exposure (`com.xrcore.ai.mcp`)

## Reference flow

```text
User Prompt
  -> XRCore LLM Bridge (route + orchestration)
  -> XRCapabilityRegistryRuntime
  -> XRCore domain capability execution
  -> XRToolExecutionResult
  -> Normalized response in XR UI
```
