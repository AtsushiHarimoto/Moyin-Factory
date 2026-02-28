# S2: Material System — IP Bible + Digital Asset Manager

## Purpose

Centralized repository for all IP settings and media assets. Serves as the single source of truth for the entire creative pipeline.

## Capabilities

- **IP Construction Engine**: LLM-guided world-building and character creation workflows
- **Asset Lifecycle Management**: Version-controlled storage with full audit trail
- **Export Engine**: Downstream packaging for novel/drama/game pipelines
- **CJK-Aware Search**: Full-text search via Meilisearch with Chinese/Japanese/Korean optimization

## Material Hierarchy

Manages the L0→L5 material refinement pipeline, enforcing Quality Gate validation at each transition.

## Technology

- Python FastAPI
- MongoDB (documents) + MinIO (object storage)
- Celery workers for async processing (migration to Temporal planned for unified orchestration with S1)
- Meilisearch for full-text search

## Key Insight

S2 is a *reference library*, not a production tool. It stores and organizes IP data that downstream systems (S3, P4, C1) consume.
