# Architecture Decision Records (ADR)

## Index

| ADR | Title | Status | Date | Summary |
|-----|-------|--------|------|---------|
| [ADR-001](adr-001-frontend-tech-stack.md) | Frontend Technology Stack | Deprecated | 2024-12 | Vue 3 for MVP phase; React 19 migration planned post-MVP |
| [ADR-002](adr-002-w1-deprecation.md) | W1 (legacy Vue 2 prototype) Deprecation | Accepted | 2025-01 | Novel writing → S3 Story Workshop; Drama → P4 Pipeline |
| [ADR-003](adr-003-audio-gateway-expansion.md) | P2 Audio Gateway Expansion | Proposed | 2025-02 | Extend from TTS-only to multi-modal audio (BGM + SFX) |
| [ADR-004](adr-004-meilisearch-for-s2.md) | S2 Search with Meilisearch | Proposed | 2025-02 | CJK-aware full-text search for materials |

## ADR Format

Each ADR follows this structure:

- **Status**: Proposed → Accepted → Deprecated / Superseded
- **Context**: What problem or situation motivated this decision?
- **Decision**: What was decided?
- **Consequences**: What are the trade-offs and implications?

## Key Decisions Summary

### ADR-001: Frontend Tech Stack

**Context**: Needed a frontend framework for the game engine and dashboard UIs.

**Decision**: Vue 3 + TypeScript for MVP phase, with planned migration to React 19 post-MVP for ecosystem breadth.

**Status**: Deprecated — React migration underway for new subsystems; Vue 3 retained for existing components.

### ADR-002: W1 Moyin Web Deprecation

**Context**: The original Moyin Web (W1, legacy Vue 2 prototype) combined novel writing and drama production in a single monolithic app.

**Decision**: Decompose W1 into specialized subsystems: novel functions → S3 Story Workshop, drama production → P4 Drama Pipeline.

**Consequences**: Better separation of concerns; each system can evolve independently.

### ADR-003: Audio Gateway Expansion

**Context**: P2 initially served only TTS. Drama production (P4) and game engine (C1) need BGM and SFX as well.

**Decision**: Extend P2 into a multi-modal audio gateway with unified provider interface for TTS, BGM, and SFX.

**Consequences**: Single integration point for all audio; provider-agnostic consumer code.

### ADR-004: Meilisearch for S2

**Context**: MongoDB text search has poor CJK (Chinese/Japanese/Korean) support for material system queries.

**Decision**: Add Meilisearch as a dedicated search engine with CJK tokenization.

**Consequences**: Better search UX for non-Latin content; additional infrastructure dependency.
