# Moyin Glossary

## Core Concepts

| Term | Definition |
|------|-----------|
| **Moyin (沫引)** | The platform name; an AI-powered IP materialization system |
| **IP** | Intellectual Property; the story world, characters, and narrative rules |
| **IP Bible** | The authoritative reference document containing all IP settings |
| **Canon** | Official story rules used to detect LLM contradictions |
| **Quality Gate (QG)** | Checkpoint validation when materials transition between L-levels |
| **Manifest (L4)** | A versioned, immutable collection of assets for a specific publication |

## Architecture Terms

| Term | Definition |
|------|-----------|
| **Moyin-LLM-Protocol** | Standardized JSON format for game turn requests/responses |
| **MCP** | Model Context Protocol; standard interface for AI agent integration |
| **Provider** | A backend service (LLM, TTS, BGM, SFX, video generation, etc.) |
| **Temporal** | Workflow orchestration engine for long-running async GPU tasks |
| **Dual-Channel** | Architecture pattern separating Human (REST/WS) and AI (MCP) channels |

## Subsystem Codes

| Code | Name | Layer |
|------|------|-------|
| S1 | Moyin OS | Platform |
| S2 | Material System | Platform |
| S3 | Story Workshop | Platform |
| A1 | MCP Server | AI Protocol |
| P1 | Moyin-ComfyUI | Production |
| P2 | Audio Gateway | Production |
| P3 | Model Trainer | Production |
| P4 | Drama Pipeline | Production |
| C1 | Moyin Game | Consumer |
| I1 | Moyin Gateway | Infrastructure |
| I2 | Ollama | Infrastructure |
| I3 | Data Layer | Infrastructure |
| X1 | Brand Design | Cross-cutting |

## Material Levels

| Level | Name | Example |
|-------|------|---------|
| L0 | Raw Inspiration | Unprocessed notes, reference images |
| L1 | Organized Material | Tagged and categorized inputs |
| L2 | IP Core | Character profiles, world settings |
| L3 | Generated Assets | Illustrations, voice files, backgrounds |
| L4 | Publication Manifest | Versioned bundle for release |
| L5 | Training Data | LoRA fine-tuning datasets |

## Production Terms

| Term | Definition |
|------|-----------|
| **LoRA** | Low-Rank Adaptation; efficient model fine-tuning technique |
| **ComfyUI** | Node-based visual workflow engine for AI image/video generation |
| **TTS** | Text-to-Speech; converts text dialogue into character voice audio |
| **BGM** | Background Music; AI-generated ambient music |
| **SFX** | Sound Effects; AI-generated sound effects |
| **VN** | Visual Novel; interactive story game format |
| **Live2D** | 2D character animation technology for real-time expression changes |

## Game Engine Terms

| Term | Definition |
|------|-----------|
| **Turn** | A single player action → LLM response → validation cycle |
| **Judge** | Validation layer that checks LLM output against schema and Canon |
| **Session** | A persistent game state tracked via append-only commits |
| **STM/LTM** | Short-Term / Long-Term Memory for character context retention |
| **Choice** | Hard-coded branching point in the story graph |
