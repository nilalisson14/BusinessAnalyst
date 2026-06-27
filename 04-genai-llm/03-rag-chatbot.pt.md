# Chatbot RAG + Guardrails (Projeto Próprio)

> [🇺🇸 English](03-rag-chatbot.en.md) · [← Voltar ao índice](../README.pt.md)

| | |
| --- | --- |
| **Tipo** | Projeto próprio / estudo de caso técnico |
| **Papel** | Concepção, arquitetura e implementação |
| **Stack** | PHP + API de LLM (Gemini) + RAG lexical + guardrails |

## Objetivo

Um assistente que responde perguntas sobre o meu perfil profissional **apenas com base em uma base de conhecimento curada** — demonstrando, na prática, como construir RAG com guardrails. É também uma peça de demonstração: o pipeline é transparente e auditável.

## Arquitetura do pipeline

```
Pergunta
  │
  ▼
[1] Guardrails de entrada  → rate limit, limite de caracteres, anti-injection
  │
  ▼
[2] Retrieval (RAG lexical) → pontuação por tags e texto; limiar de aceite
  │
  ▼
[3] Montagem do prompt      → contexto recuperado + instruções
  │
  ▼
[4] LLM                     → geração da resposta (Gemini)
  │
  ▼
[5] Guardrails de saída     → validação; fora de escopo → handoff
  │
  ▼
Resposta + telemetria do pipeline
```

## Decisões de arquitetura

**Por que retrieval lexical e não vetorial (embeddings)?** A base é pequena (poucas dezenas de chunks). Retrieval lexical é **auditável**, **sem custo extra de API** e **fácil de explicar**. Para uma base grande, o passo seguinte seria embeddings + busca vetorial — mas aqui seria over-engineering. Saber *quando não* usar a ferramenta mais sofisticada é parte da decisão de arquitetura.

**Pontuação (resumo):**
- Acerto em **tag** (palavra-chave curada) = peso alto, por palavra inteira/raiz longa (evita colisões como "receita" casar "receituário").
- Acerto no **texto** do chunk = peso baixo, como reforço.
- **Limiar de aceite:** abaixo dele, a pergunta é considerada fora de escopo e o usuário é direcionado para contato direto — em vez de o modelo alucinar.

**Guardrails:** limite de taxa e de tamanho na entrada; detecção de tentativas de *prompt injection*; e, na saída, a garantia de que respostas sem contexto suficiente não são inventadas.

## Competências demonstradas

Arquitetura de RAG · engenharia de prompt · guardrails e segurança de LLM · trade-offs de design (lexical vs. vetorial) · pensamento sobre auditabilidade e degradação graciosa · implementação ponta a ponta.

## Resultado

Pipeline testado com uma suíte de perguntas (no escopo, fora de escopo e tentativas de injection) com 100% de acerto comportamental. O painel "ver pipeline" expõe, a cada resposta, os guardrails disparados, os trechos recuperados com pontuação e a latência — transformando uma caixa-preta em demonstração de engenharia.
