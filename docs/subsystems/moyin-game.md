# C1: Moyin Game — VN Engine + AI Interaction

## Purpose

Interactive visual novel player with AI-driven dialogue, enabling turn-based storytelling where player actions drive narrative evolution.

## Mechanics

- **Scene-Based Progression**: One NEXT = one frame of narrative
- **AI Turn-Based Interaction**: Player input → LLM response → Judge validation → State commit
- **Branching Stories**: Choice-point driven routing (avoids combinatorial explosion)
- **Session Persistence**: Append-only commits for deterministic replay
- **Memory System**: STM/LTM + character emotional state tracking
- **Offline Play**: IndexedDB + local Ollama fallback

## Architecture

```mermaid
flowchart LR
    Player[Player Input] --> Engine[VN Engine]
    Engine --> LLM[LLM Provider]
    LLM --> Judge[Response Judge]
    Judge --> State[State Commit]
    State --> Render[Scene Render]
```

## Technology

- Vue 3 + TypeScript frontend
- Pinia state management
- IndexedDB (Dexie) for persistence
- Electron for desktop builds

## Design Principle

**Engine is Source of Truth** — LLM generates narrative proposals only; the Judge validates against schema and Canon, and the state engine commits the final result.

## Open-Source Component

The game engine and its supporting packages are available as [Moyin-Game](https://github.com/AtsushiHarimoto/Moyin-game).
