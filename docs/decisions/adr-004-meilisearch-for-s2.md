# ADR-004: Meilisearch for S2 Search

- **Status**: Proposed
- **Date**: 2025-02
- **Deciders**: Atsushi Harimoto

## Context

MongoDB's built-in text search has poor support for CJK (Chinese/Japanese/Korean) tokenization, resulting in suboptimal search results for material system queries in S2.

## Decision

Add Meilisearch as a dedicated search engine with CJK-aware tokenization for full-text search in the Material System.

## Consequences

- Significantly improved search UX for non-Latin content
- Additional infrastructure dependency (Meilisearch service)
- Requires index synchronization between MongoDB and Meilisearch
