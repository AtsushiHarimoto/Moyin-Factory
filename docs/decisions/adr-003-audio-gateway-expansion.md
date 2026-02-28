# ADR-003: P2 Audio Gateway Expansion

- **Status**: Proposed
- **Date**: 2025-02
- **Deciders**: Atsushi Harimoto

## Context

P2 Audio Gateway initially served only TTS (Text-to-Speech). Drama production (P4) and the game engine (C1) also require BGM (background music) and SFX (sound effects).

## Decision

Extend P2 into a multi-modal audio gateway with a unified provider interface supporting TTS, BGM, and SFX generation.

## Consequences

- Single integration point for all audio needs across subsystems
- Provider-agnostic consumer code via adapter pattern
- Additional provider adapters needed for BGM and SFX backends
