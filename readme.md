# Enterprise RAG with Guardrails & Observability

A production-grade Retrieval-Augmented Generation (RAG) system built with local inference (Ollama), defensive guardrails, and full lifecycle observability.

## Key Architecture Components

- **Retrieval Engine**: In-memory dense vector search (Qdrant) paired with cross-encoder re-ranking (FlashRank) for high precision retrieval.
- **Local Model Execution**: Local inference via Ollama (`llama3.2` for chat, `nomic-embed-text` for embeddings).
- **Defensive Guardrails**:
  - *Input Rails*: PII anonymization (Microsoft Presidio) and prompt injection/jailbreak detection.
  - *Output Rails*: LLM-as-a-judge grounding validation and corporate policy enforcement.
- **Observability**: End-to-end tracing, latency profiling, and token budgeting via Langfuse.

## Setup Instructions

1. Clone repository and set up environment:
   ```bash
   git clone <repo-url>
   cd enterprise-rag
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   python -m spacy download en_core_web_sm