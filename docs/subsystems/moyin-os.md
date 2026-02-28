# S1: Moyin OS — Platform Orchestration

## Purpose

Central dispatch and coordination layer for all generation tasks across the Moyin ecosystem.

## Responsibilities

- **Task Scheduling**: Orchestrates GPU resource allocation across production subsystems
- **Canon Management**: Maintains story consistency rules and detects contradictions in LLM output
- **Quality Gate (QG)**: Enforces validation checkpoints at material level transitions (L0→L5)
- **Memory System**: Manages STM/MTM/LTM for character context across sessions

## Technology

- Python FastAPI
- Temporal workflow engine
- MongoDB + Redis

## Design Principles

- **Local-first**: All services run locally by default
- **Separation of Concerns**: OS layer coordinates but does not own domain logic
- **Human-in-the-Loop**: Canon conflicts and QG failures require human resolution
