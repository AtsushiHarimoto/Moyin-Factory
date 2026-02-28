# S3: Story Workshop — Novel Creation Pipeline

## Purpose

Independent novel writing workbench with AI assistance, supporting the full creation lifecycle from outline to publication.

## Capabilities

- **Three-Stage Generation**: Outline → Scene → Prose
- **LLM-Powered Memory**: Three-layer context system (L1/L2/L3)
- **Context System**: @ mentions + automatic Lorebook triggers
- **Version Control**: Snapshots with diff and rollback
- **Canvas Visualization**: Timeline-based story structure view
- **Export**: Markdown, PDF, and ebook formats

## Technology

- Vue 3 frontend
- Python FastAPI backend
- Temporal workflow engine
- MongoDB

## Design Principle

**Independent Workbench** — S3 owns end-to-end novel creation with zero data coupling to C1 (Game) or P4 (Drama).
