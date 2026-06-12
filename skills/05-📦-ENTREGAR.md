# 05-📦-ENTREGAR

Feche a missao.

Gere relatorio final com arquivos alterados, decisoes tomadas, testes executados, riscos restantes, pendencias e proximos passos.

Nao implemente codigo nesta etapa.

## Entrada esperada

```text
Missao:
[objetivo, especificacao aprovada, plano aprovado, implementacao e validacao]
```

## Processo

1. Releia objetivo e criterios de aceite.
2. Revise plano, implementacao e validacao.
3. Confira arquivos alterados.
4. Liste decisoes tomadas.
5. Liste testes executados e resultados.
6. Declare riscos restantes e pendencias.
7. Sugira proximos passos objetivos.
8. Feche sem abrir escopo novo.

## Saida obrigatoria

```text
Missao concluida
[resumo em 1-3 linhas]

Objetivo original
[objetivo de negocio]

Arquivos criados
- [arquivo]: [motivo]

Arquivos alterados
- [arquivo]: [motivo]

Decisoes tomadas
- [decisao]: [por que]

Testes executados
- [comando/verificacao]: [resultado]

Criterios de aceite
- [criterio]: [atendido / parcial / nao atendido]

Riscos restantes
- [risco ou "nenhum risco relevante identificado"]

Pendencias
- [pendencia ou "nenhuma pendencia identificada"]

Proximos passos
1. [acao opcional]
2. [acao opcional]
```

## Regras

- Seja honesto sobre o que foi e nao foi validado.
- Nao declare teste executado se ele nao foi executado.
- Nao oculte risco.
- Nao sugira refatoracao cosmetica.
- Se houver pendencia bloqueante, diga claramente.

## Fechamento ideal

O usuario deve conseguir ler o relatorio e entender:

- o que mudou
- por que mudou
- como foi validado
- o que ainda merece atencao
- qual e o proximo passo mais simples
