---
name: superdev-ideia
description: SuperDev 2.0 idea stage. Use when the user provides a GOAL, idea, pain, or business objective and wants a clear specification with problem, objective, scope, non-scope, acceptance criteria, success metric, assumptions, risks, and a stop point. Do not implement code.
---

# SuperDev Ideia

Alias Codex para `01-💡-IDEIA`.

Transforme uma ideia ou objetivo em especificacao clara.

Nao implemente codigo.

## Entrada

```text
GOAL:
[objetivo de negocio]
```

## Processo

1. Leia contexto do projeto quando existir em `/ai/context`.
2. Reescreva o objetivo em linguagem de negocio.
3. Identifique o problema real.
4. Defina escopo e nao escopo.
5. Defina criterios de aceite observaveis.
6. Defina metrica de sucesso simples.
7. Pare e peca aprovacao.

## Saida

```text
Objetivo de negocio
[frase clara]

Problema
[qual dor sera resolvida]

Objetivo da missao
[resultado esperado]

Escopo
- [item dentro da missao]

Nao escopo
- [item fora da missao]

Criterios de aceite
- [criterio verificavel]

Metrica de sucesso
[como saberemos que funcionou]

Suposicoes
- [suposicao relevante]

Riscos iniciais
- [risco, se houver]

Ponto de parada
Aprove esta especificacao para eu seguir para 02-📋-PLANO.
```
