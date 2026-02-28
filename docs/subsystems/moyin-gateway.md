# I1: Moyin Gateway — LLM Multi-Provider Aggregation

## Purpose

Unified LLM gateway that abstracts provider differences behind a single OpenAI-compatible API.

## Supported Providers

| Provider | Type | Use Case |
|----------|------|----------|
| Grok | Cloud | High-quality reasoning |
| Gemini | Cloud | Multimodal tasks |
| OpenAI | Cloud | General-purpose |
| Ollama | Local | Privacy-first, offline |

## Key APIs

- `/v1/chat/completions` — OpenAI-compatible chat endpoint
- `/v1/game/turn` — Moyin-LLM-Protocol for structured game responses
- `/v1/official/*` — Direct provider proxying

## Technology

- Python FastAPI
- aiohttp for async HTTP
- Pydantic for schema validation

## Design

Provider selection is transparent to consumers. The gateway handles authentication, rate limiting, and response normalization.

## Open-Source Component

Available as [Moyin-Gateway](https://github.com/AtsushiHarimoto/Moyin-gateway).
