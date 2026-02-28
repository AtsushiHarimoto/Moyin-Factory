# Moyin Roadmap

## Vision

Build a complete AI-powered IP materialization platform where creators write stories and AI handles production across three parallel output formats.

## Current Phase: Foundation (MVP)

### Completed

- [x] I1: Moyin Gateway — Multi-provider LLM aggregation
- [x] C1: Moyin Game — VN engine with AI turn-based interaction
- [x] Network Modules — Shared HTTP client library
- [x] Hermit Purple — AI trend research tool
- [x] Dev Dashboard — Developer workflow manager
- [x] X1: Brand Design System

### In Progress

- [ ] S2: Material System — IP Bible + DAM
- [ ] S3: Story Workshop — Novel creation pipeline
- [ ] P1: Moyin-ComfyUI — Visual asset generation

## Near-Term Goals

### Platform Layer

- [ ] S1: Moyin OS — Central task orchestration with Temporal
- [ ] A1: MCP Server — AI agent integration protocol
- [ ] Canon conflict detection system
- [ ] Quality Gate enforcement

### Production Layer

- [ ] P2: Audio Gateway — Multi-provider TTS/BGM/SFX
- [ ] P3: Model Trainer — LoRA fine-tuning service
- [ ] P4: Drama Pipeline — AI video production

### Infrastructure

- [ ] I4: Rust API — High-performance local inference gateway
- [ ] Docker Compose deployment stack
- [ ] GPU resource scheduler

## Long-Term Vision

- Full three-line parallel production from single IP core
- One-click publication to novel/drama/game platforms
- Community-driven IP collaboration marketplace
- Multi-user real-time editing
- Mobile client for content consumption

## Technology Direction

| Area | Current | Planned |
|------|---------|---------|
| Frontend | Vue 3 | React 19 migration |
| Backend | Python FastAPI | + Rust for perf-critical paths |
| LLM | Cloud APIs + Ollama | Custom fine-tuned models |
| Orchestration | Basic scheduling | Temporal workflows |
| Storage | MongoDB + local FS | + MinIO object storage |
| Search | MongoDB text | Meilisearch (CJK-optimized) |
