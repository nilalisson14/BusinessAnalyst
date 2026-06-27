# Artefato de Amostra — Requisitos de Interface

> [🇺🇸 English](sample-interface-requirements.en.md) · [← Voltar ao índice](../README.pt.md)

Exemplo **anonimizado** de especificação de requisitos de interface em tabela — o nível de detalhe que entrego para guiar o desenvolvimento sem ambiguidade.

---

## RI — Tela de alteração de responsável

| Campo | Tipo | Critério | Obrigatório |
| --- | --- | --- | --- |
| Responsável atual | Apresentação | Exibe o responsável vigente do item | N |
| Buscar responsável | Busca | Localiza novo usuário interno elegível pelo nome ou chave | S |
| Justificativa | Texto | Texto livre justificando a alteração | S |
| Alterar | Botão | Confirma a operação e dispara as notificações | N/A |
| Fechar | Botão | Cancela a ação e finaliza a funcionalidade | N/A |

## RI — Campo de classificação condicional

| Tipo de prescrição | Opções exibidas | Comportamento |
| --- | --- | --- |
| Comum | Duas opções | Ambas desmarcadas; seleção única obrigatória |
| Controle especial | Uma opção | Pré-selecionada e bloqueada (não editável) |

## Por que este artefato

Demonstra a tradução de regras de negócio em comportamento de interface verificável: cada campo com tipo, critério e obrigatoriedade explícitos, e o tratamento de estados condicionais. É o que reduz idas e vindas entre negócio, design e desenvolvimento.
