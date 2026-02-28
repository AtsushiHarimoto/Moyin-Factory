# Moyin System Architecture

## Overview

**Moyin** (沫引) is an AI-powered IP materialization platform that transforms story ideas into three concurrent product formats — novels, animated dramas, and interactive visual novels — all from a single IP core.

**Core Vision**: *"Your job is to write stories; AI handles the rest."*

## Architecture Layers

```mermaid
graph TB
    subgraph "Consumer Layer"
        C1[C1: Moyin Game<br/>VN Engine + AI Interaction]
    end

    subgraph "Platform Layer"
        S1[S1: Moyin OS<br/>Task Scheduling + Canon Mgmt]
        S2[S2: Material System<br/>IP Bible + DAM]
        S3[S3: Story Workshop<br/>Novel Creation Pipeline]
    end

    subgraph "AI Protocol Layer"
        A1[A1: MCP Server<br/>Model Context Protocol]
    end

    subgraph "Production Layer"
        P1[P1: Moyin-ComfyUI<br/>Visual + Audio Factory]
        P2[P2: Audio Gateway<br/>TTS / BGM / SFX]
        P3[P3: Model Trainer<br/>LoRA Fine-Tuning]
        P4[P4: Drama Pipeline<br/>AI Video Production]
    end

    subgraph "Infrastructure Layer"
        I1[I1: Moyin Gateway<br/>LLM Multi-Provider]
        I2[I2: Ollama<br/>Local LLM Inference]
        I3[I3: Data Layer<br/>MongoDB + Redis + MinIO]
    end

    C1 --> S1
    C1 --> I1
    S3 --> S1
    S3 --> S2
    S1 --> P1
    S1 --> P4
    S1 --> P3
    P1 --> I3
    P4 --> P1
    P4 --> P2
    P2 --> I2
    P3 --> I2
    I1 --> I2
    A1 --> S1
    A1 --> S2
    A1 --> S3
```

## Three-Line Parallel Production

The same IP core simultaneously drives three product lines:

| Line | System | Output |
|------|--------|--------|
| **Novel** | S3 Story Workshop | AI-assisted novels, ebooks |
| **Drama** | P4 Drama Pipeline | Anime-style short dramas |
| **Game** | C1 Moyin Game | Interactive branching VN |

## Dual-Channel Architecture

- **Human Channel**: Users interact via REST/WebSocket APIs on web/client UIs
- **AI Channel**: AI agents interact via MCP (Model Context Protocol)

## IP Material Hierarchy

Content flows through six refinement levels:

| Level | Name | Description |
|-------|------|-------------|
| L0 | Raw Inspiration | Notes, reference images, voice memos |
| L1 | Organized Materials | Tagged, partially processed inputs |
| L2 | IP Core | Story settings, character profiles, world-building |
| L3 | Assets | Character art, backgrounds, voice files |
| L4 | Manifest | Versioned asset collection for publication |
| L5 | Training Data | Datasets for LoRA model fine-tuning |

## Design Principles

1. **Local-First** — Default to local execution; cloud APIs as optional expansion
2. **Separation of Concerns** — Each subsystem owns a clear domain
3. **AI as Proposal Generator** — LLM outputs suggestions; deterministic rules enforce final state
4. **IP Bible as Single Source** — S2 is the authoritative reference for all downstream systems
5. **Three-Line Equality** — Novel, Drama, Game lines treated as equal product formats
6. **Human in the Loop** — Critical nodes require human intervention
7. **Extensible Architecture** — New providers integrated via adapter pattern

## Communication Patterns

| Pattern | Technology | Use Case |
|---------|-----------|----------|
| Synchronous | REST API | CRUD, sync queries |
| Real-time | WebSocket | Task progress, events |
| Async workflows | Temporal | Long-running GPU tasks |
| Event bus | Redis Pub/Sub | State changes, notifications |

## LLM Request Flow

```mermaid
sequenceDiagram
    participant Client as Frontend (C1/S3)
    participant GW as I1 Gateway
    participant LLM as Cloud API / I2 Ollama
    participant Judge as Response Judge

    Client->>GW: Request (Moyin-LLM-Protocol)
    GW->>LLM: Route to best provider
    LLM->>GW: Raw response
    GW->>Judge: Schema validation
    Judge->>Client: Validated response → State commit
```
