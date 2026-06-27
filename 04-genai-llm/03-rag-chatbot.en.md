# RAG + Guardrails Chatbot (Personal Project)

> [🇧🇷 Português](03-rag-chatbot.pt.md) · [← Back to index](../README.en.md)

| | |
| --- | --- |
| **Type** | Personal project / technical case study |
| **Role** | Conception, architecture, and implementation |
| **Stack** | PHP + LLM API (Gemini) + lexical RAG + guardrails |

## Goal

An assistant that answers questions about my professional profile **based only on a curated knowledge base** — demonstrating, in practice, how to build RAG with guardrails. It's also a demo piece: the pipeline is transparent and auditable.

## Pipeline architecture

```
Question
  │
  ▼
[1] Input guardrails    → rate limit, character limit, anti-injection
  │
  ▼
[2] Retrieval (lexical RAG) → scoring by tags and text; acceptance threshold
  │
  ▼
[3] Prompt assembly     → retrieved context + instructions
  │
  ▼
[4] LLM                 → response generation (Gemini)
  │
  ▼
[5] Output guardrails   → validation; out-of-scope → handoff
  │
  ▼
Response + pipeline telemetry
```

## Architecture decisions

**Why lexical retrieval rather than vector (embeddings)?** The base is small (a few dozen chunks). Lexical retrieval is **auditable**, has **no extra API cost**, and is **easy to explain**. For a large base, the next step would be embeddings + vector search — but here that would be over-engineering. Knowing *when not* to use the more sophisticated tool is part of the architecture decision.

**Scoring (summary):**
- A **tag** hit (curated keyword) = high weight, by whole word/long root (avoids collisions like "receipt" matching "prescription").
- A **text** hit in the chunk = low weight, as reinforcement.
- **Acceptance threshold:** below it, the question is considered out of scope and the user is directed to direct contact — instead of the model hallucinating.

**Guardrails:** rate and size limits on input; detection of *prompt injection* attempts; and, on output, the guarantee that responses without sufficient context are not fabricated.

## Demonstrated skills

RAG architecture · prompt engineering · guardrails and LLM safety · design trade-offs (lexical vs. vector) · thinking about auditability and graceful degradation · end-to-end implementation.

## Outcome

Pipeline tested with a suite of questions (in-scope, out-of-scope, and injection attempts) with 100% behavioral accuracy. The "view pipeline" panel exposes, for each response, the triggered guardrails, the retrieved snippets with scores, and the latency — turning a black box into an engineering demonstration.
