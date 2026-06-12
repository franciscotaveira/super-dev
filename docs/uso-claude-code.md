# Uso no Claude Code

## Como chamar

No Claude Code, cole a skill desejada ou referencie os arquivos:

```text
Use os arquivos:
/skills/00-🧠-SUPERDEV.md
/skills/01-💡-IDEIA.md

GOAL:
[seu objetivo de negocio]
```

## Fluxo recomendado

Execute uma etapa por conversa ou por chamada:

1. Ideia
2. Plano
3. Construir
4. Testar
5. Entregar

## Cuidados

- Peca para o Claude Code ler `/ai/context` antes de planejar ou construir.
- Nao autorize implementacao enquanto a especificacao e o plano nao estiverem aprovados.
- Se ele tentar expandir escopo, peca para voltar ao plano.
