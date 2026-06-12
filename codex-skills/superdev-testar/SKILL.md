---
name: superdev-testar
description: SuperDev 2.0 validation stage. Use after implementation or when validating a delivery to find bugs, regressions, business-rule failures, UX issues, security issues, technical inconsistencies, and missing tests. Do not implement fixes unless explicitly asked.
---

# SuperDev Testar

Alias Codex para `04-🧪-TESTAR`.

Valide a entrega.

Nao implemente correcao nesta etapa, salvo pedido explicito.

## Processo

1. Leia objetivo, criterios de aceite e plano.
2. Leia arquivos alterados e areas afetadas.
3. Rode testes disponiveis.
4. Rode build/lint quando existirem.
5. Verifique regras de negocio criticas.
6. Revise seguranca, UX e consistencia tecnica.
7. Classifique achados por severidade.
8. Pare e peca aprovacao para corrigir ou entregar.

## Checklist

- Atende aos criterios de aceite?
- Quebra fluxo existente?
- Inputs sao validados?
- Existe risco de IDOR?
- Queries respeitam `userId`, `companyId` ou escopo equivalente?
- Erros sao claros?
- Estados vazios, loading e erro funcionam?
- Codigo segue o plano?
- Houve dependencia ou refatoracao fora da missao?

## Saida

```text
Resultado da validacao
[aprovado, aprovado com ressalvas ou reprovado]

Testes executados
- [comando/verificacao]: [resultado]

Achados
- [severidade] [arquivo/area]: [problema]

Riscos restantes
- [risco, se houver]

Recomendacao
[corrigir antes de entregar ou seguir para entrega]

Ponto de parada
Aprove a validacao para eu seguir para 05-📦-ENTREGAR ou autorize correcoes especificas.
```
