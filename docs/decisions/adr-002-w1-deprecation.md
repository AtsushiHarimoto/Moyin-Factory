# ADR-002: W1 Moyin Web Deprecation

- **Status**: Accepted
- **Date**: 2025-01
- **Deciders**: Atsushi Harimoto

## Context

The original Moyin Web (W1, legacy Vue 2 prototype) combined novel writing and drama production in a single monolithic application, making independent evolution difficult.

## Decision

Decompose W1 into specialized subsystems: novel writing functions migrate to S3 Story Workshop, and drama production functions migrate to P4 Drama Pipeline.

## Consequences

- Better separation of concerns; each system evolves independently
- W1 codebase is archived and no longer maintained
- Migration requires mapping legacy features to new subsystem APIs
