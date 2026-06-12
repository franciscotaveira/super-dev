# SuperDev 2.0

SuperDev 2.0 e um Sistema Operacional de Engenharia orientado a objetivos.

Ele existe para ajudar agentes de desenvolvimento como Codex, Claude Code, Cursor e Windsurf a trabalhar com mais clareza, seguranca e foco, sem virar uma skill gigante que tenta fazer tudo ao mesmo tempo.

## Ideia central

Toda missao comeca por um objetivo de negocio.

Ruim:

```text
Criar tabela de leads.
```

Bom:

```text
Garantir que nenhum lead fique sem follow-up.
```

O agente deve entender o objetivo, respeitar o contexto do projeto, planejar antes de construir, validar antes de entregar e parar nos checkpoints.

## Estrutura

```text
/skills
  00-🧠-SUPERDEV.md
  01-💡-IDEIA.md
  02-📋-PLANO.md
  03-🔨-CONSTRUIR.md
  04-🧪-TESTAR.md
  05-📦-ENTREGAR.md

/ai/context
  vision.md
  business-rules.md
  sales-process.md
  architecture.md
  decision-log.md
  mission-template.md

/docs
  audit-superdev-v1.md
  uso-codex.md
  uso-claude-code.md
  uso-cursor.md
  uso-windsurf.md

/examples
  fluxo-completo.md
  goal-follow-up-leads.md
  goal-corrigir-login.md
```

## Como usar

### 1. Transformar objetivo em especificacao

```text
Use:
00-🧠-SUPERDEV
+
01-💡-IDEIA

GOAL:
Garantir que nenhum lead fique sem follow-up.
```

Ao final, o agente deve parar e pedir aprovacao.

### 2. Criar plano tecnico

```text
Use:
00-🧠-SUPERDEV
+
02-📋-PLANO

Especificacao aprovada:
[cole ou referencie a especificacao]
```

Ao final, o agente deve parar e pedir aprovacao.

### 3. Construir

```text
Use:
00-🧠-SUPERDEV
+
03-🔨-CONSTRUIR

Plano aprovado:
[cole ou referencie o plano]
```

O agente executa somente o plano aprovado.

### 4. Testar

```text
Use:
00-🧠-SUPERDEV
+
04-🧪-TESTAR

Entrega para validar:
[cole resumo, diff ou referencia dos arquivos]
```

O agente procura bugs, regressoes, falhas de regra de negocio, UX, seguranca e inconsistencias tecnicas.

### 5. Entregar

```text
Use:
00-🧠-SUPERDEV
+
05-📦-ENTREGAR

Missao:
[cole objetivo, plano, implementacao e testes]
```

O agente fecha a missao com relatorio final.

## Regras de ouro

- Uma etapa por vez.
- Contexto antes de codigo.
- Objetivo de negocio antes de tarefa tecnica.
- Simples antes de sofisticado.
- Nenhum escopo novo durante a construcao.
- Nenhum arquivo fora da missao.
- Validar inputs, proteger escopo por `userId`/`companyId` quando aplicavel e nunca expor segredos.
- Testar sempre que houver implementacao.

## Quando usar cada skill

| Skill | Quando usar | Implementa codigo? |
| --- | --- | --- |
| `00-🧠-SUPERDEV` | Sempre, como governanca da missao | Nao |
| `01-💡-IDEIA` | Quando existe um objetivo ainda bruto | Nao |
| `02-📋-PLANO` | Quando a especificacao ja foi aprovada | Nao |
| `03-🔨-CONSTRUIR` | Quando o plano tecnico ja foi aprovado | Sim |
| `04-🧪-TESTAR` | Depois da implementacao ou para validar uma entrega | Nao, salvo correcao explicitamente pedida |
| `05-📦-ENTREGAR` | Para fechar a missao com relatorio final | Nao |

## Filosofia

SuperDev 2.0 nao e um framework academico.

E um modo de trabalhar:

1. Entender.
2. Planejar.
3. Construir.
4. Testar.
5. Entregar.

Com calma, clareza e checkpoints.
