# LLM Bridge Audit vs XRCore.AI

## Scope

Audit target: `Assets/XRCoreLLBridge`  
Reference capability layer: `Assets/XRCoreAI`

## Layer structure validation

Validated folders:

- `Runtime/Contracts`
- `Runtime/Providers`
- `Runtime/Prompting`
- `Runtime/Conversations`
- `Runtime/ToolCalling`
- `Runtime/Events`
- `Runtime/AnalyticsTraces`
- `Samples`
- `Documentation`

Result: **PASS**. Runtime boundaries are explicitly separated and aligned to the Spatial Intelligence Stack role.

## Forbidden content checks

Checked for forbidden concerns inside `Runtime`:

- Training logic: **PASS** (no training workflow/business logic; only capability routing bridge)
- MCP-specific logic: **PASS** (no MCP runtime coupling)
- OpenAI hard coupling: **PASS** (provider abstraction stays in `ILLMProvider`; OpenAI-compatible provider is optional and replaceable)
- Editor-only runtime pollution: **PASS** (`UnityEditor` APIs are confined to `Editor/`)

## AI integration contract

`XRCore LLM Bridge` integrates with `XRCore.AI` using conditional asmdefs:

- `Runtime/AIIntegration/XRCore.LLBridge.AI.asmdef`
- `Samples/Scripts/AIIntegration/XRCore.LLBridge.Samples.AI.asmdef`

This keeps `com.xrcore.ai` optional at package level while enabling executable capability registration when present.

## Capability registration status

Registered executable LLM capabilities:

- `llm.generate_response`
- `llm.route_prompt`
- `llm.summarize_context`
- `llm.execute_capability`
- `llm.normalize_response`

Flow implemented:

`LLM Bridge -> XRCapabilityRegistryRuntime -> XRCore capability -> XRToolExecutionResult -> normalized response`
