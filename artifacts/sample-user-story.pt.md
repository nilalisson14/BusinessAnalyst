# Artefato de Amostra — História de Usuário com BDD/Gherkin

> [🇺🇸 English](sample-user-story.en.md) · [← Voltar ao índice](../README.pt.md)

Exemplo **anonimizado** do meu padrão de escrita de histórias de usuário com critérios de aceite em BDD. Baseado em trabalho real de saúde regulada, com dados fictícios.

---

## História de usuário

> **Eu, como** Farmácia,
> **necessito** consultar e registrar a utilização das prescrições emitidas com numeração gerada pelo sistema,
> **a fim de** garantir controle sanitário e evitar reutilização indevida.

**Pré-condição:** existir prescrição com numeração válida e ativa.
**Ator:** estabelecimento dispensador (farmácia).
**Pós-condição:** numeração marcada como utilizada e indisponível para reutilização.

## Critérios de aceite (BDD/Gherkin)

```gherkin
Funcionalidade: Baixa e validação de prescrição pela farmácia

  Cenário: Consulta pública da prescrição
    Dado que a farmácia necessita validar a prescrição
    Quando a farmácia acessar o sistema com o número
    Então deve ser possível verificar o status e a validade da numeração

  Cenário: Campo de classificação condicional (prescrição comum)
    Dado que o usuário acessa o registro com uma prescrição comum
    Quando o sistema carrega a tela
    Então deve exibir as duas opções de classificação desmarcadas
    E exigir a seleção de uma para prosseguir

  Cenário: Campo de classificação condicional (controle especial)
    Dado que o usuário acessa o registro com uma prescrição de controle especial
    Quando o sistema carrega o campo
    Então deve exibir apenas a opção aplicável, marcada e bloqueada

  Cenário: Exclusividade de seleção
    Dado que o usuário seleciona uma das opções
    Quando a seleção ocorre
    Então o sistema desmarca automaticamente a outra opção

  Cenário: Bloqueio por campo obrigatório
    Dado que o usuário não selecionou nenhuma opção obrigatória
    Quando tenta avançar
    Então o sistema bloqueia o avanço e exibe mensagem de obrigatoriedade

  Cenário: Impossibilidade de reutilização
    Dado que a farmácia registra a dispensação com o número gerado
    Quando o sistema recebe a informação
    Então o número é automaticamente bloqueado para utilizações futuras
```

## Por que este artefato

Demonstra escrita de histórias claras e testáveis, critérios de aceite em formato executável (BDD), tratamento de comportamento condicional e de casos de borda (obrigatoriedade, exclusividade) e atenção a regras de conformidade (antirreutilização).
