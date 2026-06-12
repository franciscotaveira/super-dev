# 01-💡-IDEIA

Transforme uma ideia ou objetivo em especificacao clara.

Entrada principal:

```text
GOAL:
[objetivo de negocio]
```

Nao implemente codigo.

Nao crie plano tecnico detalhado.

## Quando usar

Use quando o usuario tem uma ideia, dor, objetivo ou problema ainda bruto.

Exemplos:

- "Quero melhorar o follow-up de leads."
- "Os usuarios estao abandonando o cadastro."
- "Preciso evitar perda de propostas."
- "GOAL: garantir que nenhum lead fique sem follow-up."

## Processo

1. Leia o contexto do projeto, se existir:
   - `/ai/context/vision.md`
   - `/ai/context/business-rules.md`
   - `/ai/context/sales-process.md`
   - `/ai/context/architecture.md`
   - `/ai/context/decision-log.md`
2. Reescreva o objetivo em linguagem de negocio.
3. Identifique o problema real.
4. Defina escopo e nao escopo.
5. Defina criterios de aceite observaveis.
6. Defina metrica de sucesso simples.
7. Pare e peca aprovacao.

## Saida obrigatoria

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

## Boas praticas

- Escreva simples.
- Evite termos tecnicos quando o problema ainda e de negocio.
- Se o GOAL vier como tarefa tecnica, traduza para objetivo.
- Se faltar informacao, faca no maximo perguntas essenciais.
- Se a falta de informacao nao bloquear, declare a suposicao e siga.

## Proibido nesta etapa

- alterar codigo
- listar implementacao linha a linha
- escolher biblioteca nova
- criar migracao
- refatorar
- executar testes
- pular direto para entrega
