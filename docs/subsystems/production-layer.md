# Production Layer — P1 / P2 / P3 / P4

## P1: Moyin-ComfyUI — Visual + Audio Asset Factory

Production pipeline for all visual and audio generation using ComfyUI as the workflow engine.

**Capabilities**: Character illustration, background scenes, expression sheets, Live2D decomposition, video generation, BGM/SFX generation.

**Architecture**: ComfyUI workflow engine + FastAPI REST + Temporal Activity workers.

**Principle**: "Workflow-driven" — all generation logic lives in ComfyUI JSON workflows; P1 orchestrates execution.

---

## P2: Audio Gateway — Multi-Provider TTS / BGM / SFX

Unified audio generation gateway supporting multiple providers behind a single abstract interface.

**TTS Providers**: IndexTTS-2, CosyVoice 2, Kokoro, GPT-SoVITS, Orpheus
**BGM Providers**: ACE-Step, DiffRhythm, YuE
**SFX Providers**: AudioLDM 2, EzAudio

**Features**: Emotion standardization, duration control for sync, provider health monitoring.

---

## P3: Model Trainer — LoRA Fine-Tuning Service

Trains custom LoRA models for story-specific generation.

**Dual-Model Architecture**:
- **Story Control Layer**: Structured JSON output for game state decisions
- **Character Tone Layer**: Dialogue generation with character-specific voice

**Base Model**: Qwen2.5-7B-Instruct
**Output**: Auto-deployed to Ollama + registered as Gateway providers.

---

## P4: Drama Pipeline — AI Video Production

7-stage pipeline transforming novel text into anime-style drama videos:

1. Script processing
2. Storyboard generation
3. Character/scene design
4. Image generation (Stable Diffusion)
5. Video generation (Wan/Kling AI)
6. Audio synthesis (TTS + BGM + SFX)
7. Compositing/export (FFmpeg)

**Key Features**: Character consistency (ArcFace scoring), multi-character composition, cost tracking.

**Philosophy**: AI-driven with human checkpoints at critical nodes.
