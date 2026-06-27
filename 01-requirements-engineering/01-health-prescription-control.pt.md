# Controle Sanitário de Prescrições — Sistema Nacional de Controle de Receituário

> [🇺🇸 English](01-health-prescription-control.en.md) · [← Voltar ao índice](../README.pt.md)

| | |
| --- | --- |
| **Domínio** | Saúde pública, vigilância sanitária, medicamentos de controle especial |
| **Papel** | Analista de Requisitos / Engenheiro de Requisitos |
| **Formato** | Histórias de usuário com critérios de aceite em BDD/Gherkin |
| **Entrega** | 52 telas prototipadas + histórias de usuário |

## Contexto e objetivo

Sistema nacional que centraliza o controle de prescrições de medicamentos sob vigilância sanitária. Atuei na concepção e no detalhamento dos requisitos de todo o ciclo de vida da numeração de receitas controladas: geração, expedição entre órgãos de vigilância, atribuição a prescritores e instituições, dispensação na farmácia, cancelamento e monitoramento — com rastreabilidade ponta a ponta entre a agência reguladora, órgãos estaduais e municipais, gráficas, instituições, prescritores e estabelecimentos dispensadores.

## Escopo funcional documentado

**Geração e distribuição de numeração**
- Geração e cancelamento de solicitação de numeração, com tipo de emissão (física ou eletrônica) e quantidade.
- Guia de requisição para gráfica e fluxo de expedição/recebimento entre órgãos, com comprovantes.
- Cadastro de gráficas e template de impressão (formato, papel, numeração, picote).

**Atribuição e dispensação**
- Atribuição a prescritores e instituições com regras distintas por tipo de receita.
- Registro de dispensação diferenciando medicamento industrializado de manipulado, com controle de lote, registro e substância controlada.
- Prescrições de uso único, prolongado e parcial, com formulário incremental e regras de visibilidade entre estabelecimentos.
- Cancelamento de utilização com trilha de auditoria.

**Consultas, cancelamentos e monitoramento (BI)**
- Consulta pública na base nacional, com estados Autorizada, Utilizada, Utilizada Parcialmente e Expirada.
- Cancelamento total e parcial, com motivos padronizados e justificativa obrigatória.
- Painéis de monitoramento de baixa, rankings, exportação CSV e indicadores de SLA por órgão.

## Atores e perfis

Agência reguladora, órgão de vigilância estadual e municipal, gráfica, instituição (hospital/unidade de saúde), prescritor e estabelecimento dispensador (farmácia), cada um com regras de visibilidade e ações próprias.

## Competências aplicadas

Discovery com stakeholders em contexto institucional complexo · mapeamento de processos regulatórios · requisitos funcionais e não funcionais · histórias de usuário claras e testáveis · critérios de aceitação em BDD · prototipação de telas (UX) · modelagem de regras sensíveis a conformidade, com atenção a rastreabilidade, auditoria e proteção de dados de saúde.

## Resultado

Ciclo de vida da numeração de prescrições especificado de ponta a ponta, com baixa automática que impede reutilização indevida — objetivo central de controle sanitário. Requisitos rastreáveis e alinhados aos protótipos, reduzindo retrabalho entre negócio e desenvolvimento em ambiente de alta criticidade.
