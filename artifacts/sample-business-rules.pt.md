# Artefato de Amostra — Regras de Negócio

> [🇺🇸 English](sample-business-rules.en.md) · [← Voltar ao índice](../README.pt.md)

Exemplos **anonimizados** de regras de negócio que especifiquei, em dois domínios distintos. Demonstram integridade, conformidade e cálculo.

---

## Domínio 1 — Governança de acesso (troca de responsável)

| ID | Regra |
| --- | --- |
| RN01 | O sistema exige registro de termo de aceite (declaração de não conflito de interesses) antes de o novo responsável operar o item. |
| RN02 | O sistema mantém histórico do responsável anterior; o termo anterior não é apagado, apenas marcado como finalizado, com data e justificativa. |
| RN03 | Só é permitido um termo de aceite ativo por responsável. |
| RN04 | Só é permitido vincular usuários internos ativos; não se permite colaborador externo, nem o responsável atual, nem quem já tenha outro papel conflitante no mesmo item. |
| RN05 | A alteração só é permitida em itens nos estados elegíveis (ex.: Submetido, Publicado, em Julgamento, em Seleção). |

## Domínio 2 — Integridade hierárquica e cálculo (financeiro)

| ID | Regra |
| --- | --- |
| RN06 | Todo item vincula-se a um produto/subproduto, que vincula-se a um componente, que vincula-se a um tipo de custo de um programa. Sem associação válida, a inclusão é bloqueada. |
| RN07 | Nenhum nível pode ter valor maior que o orçamento do nível ao qual está associado. |
| RN08 | Valor estimado do componente = soma dos produtos; do produto = soma dos subprodutos; valor consumido = soma dos itens. |
| RN09 | Conversão cambial usa a cotação do respectivo programa na data da operação. |
| RN10 | Um desembolso entra como crédito; a entrada efetiva exige operação de internalização, com declaração do valor em moeda estrangeira e local conforme o câmbio da data. |

## Por que este artefato

Mostra dois tipos de regra que aparecem com frequência: **governança/conformidade** (controle de acesso, auditoria, conflito de interesses) e **integridade de dados com cálculo** (hierarquia, limites orçamentários, conversão). Regras escritas de forma atômica, verificável e rastreável.
