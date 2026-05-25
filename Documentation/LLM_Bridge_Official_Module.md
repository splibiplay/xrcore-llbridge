# XRCore LLM Bridge Official Module Definition

## Official role

`XRCore LLM Bridge` is the official LLM orchestration module of the Spatial Intelligence Stack.

It is responsible for:

- provider abstraction for language model backends,
- prompt routing and tool/capability planning,
- response normalization,
- event and analytics trace emission for XR runtime observability.

It is explicitly **not**:

- an autonomous agent runtime,
- a training-logic module,
- an MCP adapter.

## Canonical architecture

```text
XRCore Events / Voice / Vision / Context
        ↓
XRCore LLM Bridge
        ↓
Provider Abstraction (OpenAI-compatible / Ollama / LM Studio / Azure / Mock)
        ↓
Normalized LLM Response
        ↓
XRCoreEventBus + XRCapabilityRegistry + Analytics
```

## Dependency model

- Required: `com.xrcore.sdk`, `com.xrcore.context`, `com.xrcore.voice`
- Optional: `com.xrcore.ai` (conditional capability registration path)
- No MCP dependency

## Public capability surface (when AI present)

- `llm.generate_response`
- `llm.route_prompt`
- `llm.summarize_context`
- `llm.execute_capability`
- `llm.normalize_response`

## Mandatory demo

Demo scene: `Assets/XRCoreLLBridge/Samples/Demo_LLM_Capability_Assistant.unity`

Demonstrates:

1. User prompt input
2. LLM route resolution
3. Capability call through `XRCapabilityRegistryRuntime`
4. Mock downstream capability execution (training/context/voice)
5. Response normalization and XR UI feedback
