---
name: superdev-plano
description: SuperDev 2.0 planning stage. Use after an approved specification to create a technical plan with affected files, implementation strategy, execution order, risks, mitigations, impacts, planned validation, and out-of-plan items. Do not edit files or implement code.
---

# SuperDev Plano

Alias Codex para `02-📋-PLANO`.

Transforme uma especificacao aprovada em plano tecnico.

Nao implemente codigo.

## Processo

1. Leia a especificacao aprovada.
2. Leia contexto tecnico em `/ai/context` quando existir.
3. Inspecione o projeto apenas o suficiente para planejar.
4. Liste arquivos provaveis afetados.
5. Defina estrategia de implementacao.
6. Identifique riscos, impactos e validacoes.
7. Defina ordem de execucao.
8. Pare e peca aprovacao.

## Saida

```text
Resumo da especificacao
[objetivo aprovado em 1-3 linhas]

Arquivos afetados
- [arquivo ou area]: [motivo]

Estrategia de implementacao
- [decisao tecnica simples]

Ordem de execucao
1. [passo]
2. [passo]
3. [passo]

Riscos e mitigacoes
- [risco]: [mitigacao]

Impactos
- Negocio: [impacto]
- Tecnico: [impacto]
- UX: [impacto, se houver]
- Seguranca: [impacto, se houver]

Validacao planejada
- [teste, lint, build ou verificacao manual]

Fora do plano
- [o que nao sera feito]

Ponto de parada
Aprove este plano para eu seguir para 03-🔨-CONSTRUIR.
```
