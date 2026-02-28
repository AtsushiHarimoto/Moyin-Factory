# ADR-001: Frontend Technology Stack

- **Status**: Deprecated
- **Date**: 2024-12
- **Deciders**: Atsushi Harimoto

## Context

The Moyin platform needed a frontend framework for the game engine (C1) and dashboard UIs. Key requirements included reactive state management, TypeScript support, and component-based architecture.

## Decision

Adopt Vue 3 + TypeScript + Pinia for the MVP phase, with a planned migration to React 19 post-MVP for broader ecosystem access.

## Consequences

- Vue 3 retained for existing components (e.g., C1 Moyin Game)
- New subsystems (e.g., Dev-Dashboard) use React
- Dual-framework maintenance during transition period
