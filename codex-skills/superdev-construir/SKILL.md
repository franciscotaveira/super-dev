---
name: superdev-construir
description: SuperDev 2.0 build stage. Use only after an approved technical plan to implement exactly that plan, without new scope, unrelated refactors, or unrelated file changes. Preserve user changes, security, clean code, and run planned validation.
---

# SuperDev Construir

Alias Codex para `03-🔨-CONSTRUIR`.

Execute somente o plano aprovado.

## Regras

- Nao crie escopo novo.
- Nao refatore fora do combinado.
- Nao altere arquivos fora da missao.
- Preserve alteracoes existentes do usuario.
- Se precisar mudar o plano, pare e explique antes de continuar.

## Processo

1. Confirme o plano aprovado.
2. Leia os arquivos citados no plano.
3. Verifique alteracoes locais antes de editar.
4. Implemente em passos pequenos.
5. Mantenha nomes claros e funcoes pequenas.
6. Valide inputs e erros.
7. Preserve escopo por `userId`/`companyId` quando aplicavel.
8. Rode validacao planejada.
9. Pare com resumo tecnico e resultado dos testes.

## Saida

```text
Implementacao concluida
- [o que foi alterado]

Arquivos alterados
- [arquivo]: [motivo]

Validacao executada
- [comando/verificacao]: [resultado]

Desvios do plano
- [nenhum ou explicar]

Riscos restantes
- [risco, se houver]

Ponto de parada
Aprove a implementacao para eu seguir para 04-🧪-TESTAR.
```
