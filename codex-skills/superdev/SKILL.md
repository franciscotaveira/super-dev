---
name: superdev
description: SuperDev 2.0 governance skill for goal-driven engineering. Use with one stage alias such as superdev-ideia, superdev-plano, superdev-construir, superdev-testar, or superdev-entregar when the user wants objective-first software engineering with context-first reading, stop points, anti-overengineering, security, clean code, and validation discipline.
---

# SuperDev

Use this as the Codex-compatible alias for `00-🧠-SUPERDEV`.

## Core rule

Do not implement code with this skill alone. Pair it with exactly one stage skill unless the user explicitly asks for multiple stages.

## Stages

- `superdev-ideia`: turn GOAL into a clear specification.
- `superdev-plano`: turn approved specification into a technical plan.
- `superdev-construir`: execute only the approved plan.
- `superdev-testar`: validate implementation.
- `superdev-entregar`: close the mission with a final report.

## Principles

- Start from a business GOAL, not a technical task.
- Read project context before planning or changing code.
- Run one stage at a time.
- Stop at the end of every stage and ask approval.
- Prefer simplicity, readability, low maintenance, low operational cost, and minimal dependencies.
- Preserve input validation, IDOR protection, tenant scope by `userId`/`companyId` when applicable, explicit error handling, and secret redaction.
- Preserve clean names, small functions, separated responsibilities, and comments that explain why.
- Whenever implementing, run available tests, lint, and build; if unavailable, say so.

## Context files

Read these when they exist:

- `/ai/context/vision.md`
- `/ai/context/business-rules.md`
- `/ai/context/sales-process.md`
- `/ai/context/architecture.md`
- `/ai/context/decision-log.md`
- `/ai/context/mission-template.md`

## Stop point

End each stage with:

```text
Ponto de parada: aprove esta etapa para eu seguir para [proxima etapa].
```
