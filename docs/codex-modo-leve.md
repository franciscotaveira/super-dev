# Codex em modo leve

Use este guia quando o seletor `@` do Codex estiver carregando muitas skills e ficando lento.

## Objetivo

Deixar visiveis apenas as skills do SuperDev no uso diario:

```text
@superdev
@superdev-processo
@superdev-ideia
@superdev-plano
@superdev-construir
@superdev-testar
@superdev-entregar
```

## 1. Instalar apenas os aliases SuperDev

Copie as pastas de:

```text
codex-skills/
```

Para:

```text
C:\Users\SEU_USUARIO\.codex\skills
```

Ao final, a pasta local deve conter:

```text
superdev
superdev-processo
superdev-ideia
superdev-plano
superdev-construir
superdev-testar
superdev-entregar
```

## 2. Desativar plugins extras

Se outras skills continuarem aparecendo, elas podem vir de plugins e conectores.

Edite:

```text
C:\Users\SEU_USUARIO\.codex\config.toml
```

Antes de editar, crie backup:

```text
C:\Users\SEU_USUARIO\.codex\config.toml.backup-before-superdev-slim
```

Depois marque plugins nao usados como `enabled = false`.

Exemplo:

```toml
[plugins."openai-developers@openai-curated"]
enabled = false

[plugins."browser@openai-bundled"]
enabled = false

[plugins."chrome@openai-bundled"]
enabled = false

[plugins."canva@openai-curated-remote"]
enabled = false

[plugins."github@openai-curated-remote"]
enabled = false

[plugins."google-calendar@openai-curated-remote"]
enabled = false

[plugins."supabase@openai-curated-remote"]
enabled = false
```

## 3. Reiniciar o Codex

Abra uma nova sessao do Codex para recarregar a lista de skills.

## Como reverter

Restaure o backup:

```text
C:\Users\SEU_USUARIO\.codex\config.toml.backup-before-superdev-slim
```

Ou altere o plugin desejado de volta para:

```toml
enabled = true
```

## Observacao

Nao versionar `C:\Users\SEU_USUARIO\.codex\config.toml` dentro deste repositorio.

Esse arquivo e configuracao pessoal da maquina. O repositorio deve guardar apenas instrucoes e aliases reutilizaveis.
