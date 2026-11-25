# ORCA — Knowledge-Grounded LLM Assistant

**ORCA** (Ontology-driven Reasoning & Compliance Auditor) is a Knowledge Representation & Reasoning (KRR) project that combines a Knowledge Graph with Large Language Models to deliver grounded, verifiable, and hallucination-resistant AI answers.

## Project Summary

ORCA links user questions to real Knowledge Graph entities, retrieves verified facts and reasoning paths, and uses LLM generation only when grounded evidence exists. When queried about unknown entities the system refuses safely instead of hallucinating — making it suitable for compliance, security-policy, and access-control domains.

## Key Features

- **Unified LLM Client** — seamlessly switches between cloud Gemini 3.5 Flash-Lite API and offline local Qwen2.5-0.5B-Instruct on CPU with deterministic decoding.
- **KG-RAG Pipeline** — entity/label linking, dynamic SPARQL retrieval, anti-hallucination verification, and safe refusal on insufficient evidence.
- **Grounded Assistant** — `ask_llm_only`, `ask` (KG-grounded), and `compare_llm_vs_kg` helpers for transparent comparison.
- **Interactive Frontend** — LLM-only view, KG-grounded view with provenance bar and fired rules, and a side-by-side Compare arena with 10-CQ benchmark.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| LLM (Cloud) | Google Gemini 3.5 Flash-Lite via OpenAI-compatible API |
| LLM (Local) | HuggingFace Transformers — Qwen2.5-0.5B-Instruct (CPU) |
| Knowledge Graph | RDFLib + SPARQL |
| Backend | Python (httpx, dotenv) |
| Frontend | React + TypeScript |

## Project Structure

```
backend/
  llm_client.py      # Unified LLM client (API + local fallback)
  kg_rag.py           # KG retrieval, entity linking, refusal guardrails
  assistant.py        # Grounded assistant helpers
frontend/
  src/pages/
    LlmOnlyPage.tsx   # Standalone LLM baseline view
    LlmKgPage.tsx     # KG-grounded view with provenance
    ComparePage.tsx    # Side-by-side arena + 10-CQ benchmark
```

## Team

- **Afaq Amin** (24i-2542)

## License

This project is developed as part of a university KRR course.
