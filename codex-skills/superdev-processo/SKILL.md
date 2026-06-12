---
name: superdev-processo
description: SuperDev 2.0 process routing skill. Use when the mission is unclear, the user does not know which SuperDev stage to invoke, a paused mission must be resumed, or a request mixes idea, planning, building, testing, and delivery. Select exactly one next stage and stop for approval. Do not implement code.
---

# SuperDev Processo

Alias Codex para `00-🧭-PROCESSO`.

Use esta skill para descobrir onde a missao esta e qual etapa vem a seguir.

Nao implemente codigo.

## Fluxo

```text
GOAL
↓
superdev-processo
↓
superdev-ideia
↓
superdev-plano
↓
superdev-construir
↓
superdev-testar
↓
superdev-entregar
```

## Processo

1. Leia o pedido do usuario.
2. Identifique o estado atual da missao.
3. Verifique se existe GOAL, especificacao, plano, implementacao e validacao.
4. Escolha exatamente uma proxima etapa.
5. Explique por que essa etapa e a correta.
6. Pare e peca confirmacao.

## Decisao

| Situacao | Proxima skill |
| --- | --- |
| Apenas ideia ou GOAL bruto | `superdev-ideia` |
| Especificacao aprovada, sem plano | `superdev-plano` |
| Plano aprovado, sem implementacao | `superdev-construir` |
| Implementacao concluida, sem validacao | `superdev-testar` |
| Validacao concluida, sem relatorio | `superdev-entregar` |
| Pedido mistura varias etapas | Recomendar apenas a primeira etapa pendente |

## Saida

```text
Estado da missao
[onde estamos agora]

Contexto disponivel
- GOAL: [sim/nao]
- Especificacao aprovada: [sim/nao]
- Plano aprovado: [sim/nao]
- Implementacao concluida: [sim/nao]
- Validacao concluida: [sim/nao]

Proxima etapa recomendada
[skill recomendada]

Por que esta etapa
[explicacao curta]

O que nao farei agora
- [etapas que devem esperar]

Ponto de parada
Aprove para eu executar [skill recomendada].
```
