# Moyin Factory

> **AI-Powered IP Materialization Platform**
> *Your job is to write stories; AI handles the rest.*

[English](#overview) | [日本語](#概要) | [繁體中文](#概述)

---

## Overview

**Moyin** (沫引) is a modular platform that transforms story ideas into three concurrent product formats — novels, animated dramas, and interactive visual novels — all from a single IP core.

This repository serves as the **architecture hub** for the Moyin ecosystem, providing system design documentation, subsystem overviews, and architectural decision records.

## Ecosystem

```mermaid
graph TB
    subgraph "Open Source"
        Game["🎮 Moyin-Game<br/>VN Engine + AI Interaction"]
        Gateway["🔀 Moyin-Gateway<br/>LLM Multi-Provider"]
        Net["🌐 Network-Modules<br/>HTTP Client Library"]
        Hermit["🔮 hermit-purple<br/>AI Trend Research"]
        Dash["📊 Dev-Dashboard<br/>Workflow Manager"]
    end

    subgraph "Platform (Private)"
        OS["Moyin OS"]
        Material["Material System"]
        Workshop["Story Workshop"]
    end

    subgraph "Production (Private)"
        ComfyUI["Moyin-ComfyUI"]
        Audio["Audio Gateway"]
        Trainer["Model Trainer"]
        Drama["Drama Pipeline"]
    end

    Game --> Gateway
    Game --> Net
    Workshop --> Material
    Workshop --> Gateway
    Drama --> ComfyUI
    Drama --> Audio
    Trainer --> Gateway
    OS --> ComfyUI
    OS --> Drama
```

### Open-Source Repositories

| Repository | Description | Tech |
|-----------|-------------|------|
| [**Moyin-Game**](https://github.com/AtsushiHarimoto/Moyin-game) | Visual novel engine with AI-driven dialogue and branching stories | Vue 3, TypeScript, Pinia |
| [**Moyin-Gateway**](https://github.com/AtsushiHarimoto/Moyin-gateway) | Unified LLM gateway (Grok, Gemini, OpenAI, Ollama) | Python, FastAPI |
| [**Network-Modules**](https://github.com/AtsushiHarimoto/Moyin-Network-modules) | Shared HTTP client with deduplication and retry | TypeScript, Vitest |
| [**hermit-purple**](https://github.com/AtsushiHarimoto/hermit-purple) | AI trend research tool with multi-source crawling | Python, Gemini API |
| [**Dev-Dashboard**](https://github.com/AtsushiHarimoto/Moyin-Dev-Dashboard) | Developer workflow and AI agent skills manager | React, Express, SQLite |

## Documentation

- [`docs/architecture/`](docs/architecture/) — System overview and glossary
- [`docs/subsystems/`](docs/subsystems/) — Individual subsystem overviews
- [`docs/decisions/`](docs/decisions/) — Architecture Decision Records (ADR)
- [`docs/roadmap/`](docs/roadmap/) — Development blueprint

## Key Technical Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| **LLM Integration** | Multi-provider gateway | Provider-agnostic; switch without code changes |
| **Game State** | Append-only commits | Deterministic replay; offline-first |
| **AI Role** | Proposal generator | LLM suggests; Judge validates; Engine commits |
| **Architecture** | Local-first | Privacy by default; cloud as optional expansion |
| **IP Management** | 6-level hierarchy (L0-L5) | Structured refinement from raw idea to production |

## Design Principles

1. **Local-First** — All services run locally by default
2. **AI as Proposal Generator** — LLM outputs are always validated before commitment
3. **IP Bible as Single Source** — One authoritative reference for all downstream systems
4. **Three-Line Equality** — Novel, Drama, and Game are equal product formats
5. **Extensible via Adapters** — New providers integrate without core changes

---

## 概要

**Moyin**（沫引）は、ストーリーのアイデアを小説・アニメドラマ・インタラクティブビジュアルノベルの3つの形式に同時変換するAI駆動のIP具現化プラットフォームです。

このリポジトリは、Moyinエコシステムの**アーキテクチャハブ**として、システム設計ドキュメント、サブシステム概要、アーキテクチャ決定記録を提供します。

### オープンソースリポジトリ

| リポジトリ | 説明 | 技術 |
|-----------|------|------|
| [**Moyin-Game**](https://github.com/AtsushiHarimoto/Moyin-game) | AI対話と分岐ストーリーのビジュアルノベルエンジン | Vue 3, TypeScript |
| [**Moyin-Gateway**](https://github.com/AtsushiHarimoto/Moyin-gateway) | 統合LLMゲートウェイ（Grok, Gemini, OpenAI, Ollama） | Python, FastAPI |
| [**Network-Modules**](https://github.com/AtsushiHarimoto/Moyin-Network-modules) | 重複排除とリトライ機能付きHTTPクライアント | TypeScript |
| [**hermit-purple**](https://github.com/AtsushiHarimoto/hermit-purple) | マルチソースAIトレンドリサーチツール | Python |
| [**Dev-Dashboard**](https://github.com/AtsushiHarimoto/Moyin-Dev-Dashboard) | 開発ワークフローとAIエージェントスキル管理 | React, Express |

---

## 概述

**Moyin**（沫引）是一個 AI 驅動的 IP 具現化平台，將故事創意同時轉化為小說、動畫短劇和互動視覺小說三種產品格式。

此倉庫作為 Moyin 生態系統的**架構中心**，提供系統設計文檔、子系統概覽和架構決策記錄。

### 開源倉庫

| 倉庫 | 說明 | 技術 |
|------|------|------|
| [**Moyin-Game**](https://github.com/AtsushiHarimoto/Moyin-game) | AI 對話與分支故事的視覺小說引擎 | Vue 3, TypeScript |
| [**Moyin-Gateway**](https://github.com/AtsushiHarimoto/Moyin-gateway) | 統一 LLM 閘道（Grok, Gemini, OpenAI, Ollama） | Python, FastAPI |
| [**Network-Modules**](https://github.com/AtsushiHarimoto/Moyin-Network-modules) | 帶去重和重試的共用 HTTP 客戶端 | TypeScript |
| [**hermit-purple**](https://github.com/AtsushiHarimoto/hermit-purple) | 多源 AI 趨勢研究工具 | Python |
| [**Dev-Dashboard**](https://github.com/AtsushiHarimoto/Moyin-Dev-Dashboard) | 開發工作流與 AI 代理技能管理 | React, Express |

---

## License

This documentation is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

## Author

**Atsushi Harimoto** — [GitHub](https://github.com/AtsushiHarimoto)
