# Uso no Codex

## Importante sobre o `@`

O `@` do Codex nao lista arquivos Markdown soltos do repositorio.

Para aparecer no seletor, a skill precisa estar em formato Codex:

```text
nome-da-skill/
  SKILL.md
```

Por isso este repositorio tem duas camadas:

- `/skills`: nomenclatura visual oficial do SuperDev 2.0.
- `/codex-skills`: aliases compativeis com o `@` do Codex.

## Como chamar com `@`

Use:

```text
@superdev
@superdev-ideia

GOAL:
[seu objetivo de negocio]
```

Depois:

```text
@superdev
@superdev-plano
```

E continue com:

- `@superdev-construir`
- `@superdev-testar`
- `@superdev-entregar`

## Como chamar sem `@`

Cole no Codex:

```text
Use:
00-🧠-SUPERDEV
+
01-💡-IDEIA

GOAL:
[seu objetivo de negocio]
```

Depois aprove a etapa e chame a proxima skill.

## Instalacao local dos aliases

Copie as pastas de `/codex-skills` para sua pasta local de skills do Codex:

```text
C:\Users\SEU_USUARIO\.codex\skills
```

Depois abra uma nova conversa/sessao do Codex para recarregar a lista de skills.

## Fluxo recomendado

1. `00-🧠-SUPERDEV` + `01-💡-IDEIA`
2. `00-🧠-SUPERDEV` + `02-📋-PLANO`
3. `00-🧠-SUPERDEV` + `03-🔨-CONSTRUIR`
4. `00-🧠-SUPERDEV` + `04-🧪-TESTAR`
5. `00-🧠-SUPERDEV` + `05-📦-ENTREGAR`

## Dica operacional

Se o projeto tiver contexto em `/ai/context`, peca explicitamente:

```text
Antes de responder, leia /ai/context.
```

Codex deve parar ao final de cada etapa e aguardar aprovacao.
