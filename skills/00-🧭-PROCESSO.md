# 00-🧭-PROCESSO

Skill de orientacao do fluxo SuperDev 2.0.

Use quando a missao ainda esta confusa, quando o usuario nao sabe qual etapa chamar, ou quando e preciso retomar uma missao pausada.

Esta skill nao implementa codigo.

Ela decide qual proxima skill usar.

## Papel

Servir como mapa do processo:

```text
GOAL
↓
00-🧭-PROCESSO
↓
01-💡-IDEIA
↓
02-📋-PLANO
↓
03-🔨-CONSTRUIR
↓
04-🧪-TESTAR
↓
05-📦-ENTREGAR
```

## Quando usar

Use `00-🧭-PROCESSO` quando:

- o usuario trouxe um pedido misturado com ideia, plano e implementacao
- o usuario nao sabe por onde comecar
- a missao foi pausada e precisa ser retomada
- existe duvida se deve ir para IDEIA, PLANO, CONSTRUIR, TESTAR ou ENTREGAR
- o agente comecou a fazer etapas demais de uma vez

## Processo

1. Leia o pedido do usuario.
2. Identifique o estado atual da missao.
3. Verifique se existe contexto aprovado:
   - GOAL
   - especificacao
   - plano
   - implementacao
   - validacao
4. Escolha exatamente uma proxima etapa.
5. Explique por que essa etapa e a correta.
6. Pare e peca confirmacao para executar a etapa escolhida.

## Como decidir

| Situacao | Proxima skill |
| --- | --- |
| Existe apenas uma ideia ou GOAL bruto | `01-💡-IDEIA` |
| Existe especificacao aprovada, mas nao ha plano | `02-📋-PLANO` |
| Existe plano aprovado, mas nao foi implementado | `03-🔨-CONSTRUIR` |
| Existe implementacao, mas falta validacao | `04-🧪-TESTAR` |
| Existe validacao suficiente e falta relatorio | `05-📦-ENTREGAR` |
| O pedido mistura varias etapas | Separar e recomendar apenas a primeira etapa pendente |

## Saida obrigatoria

```text
Estado da missao
[onde estamos agora]

Contexto disponivel
- GOAL: [sim/nao]
- Especificacao aprovada: [sim/nao]
- Plano aprovado: [sim/nao]
- Implementacao concluida: [sim/nao]
- Validacao concluida: [sim/nao]

Proxima etapa recomendada
[skill recomendada]

Por que esta etapa
[explicacao curta]

O que nao farei agora
- [etapas que devem esperar]

Ponto de parada
Aprove para eu executar [skill recomendada].
```

## Regras

- Nao implemente codigo.
- Nao crie especificacao completa.
- Nao crie plano tecnico completo.
- Nao pule stop points.
- Nao execute mais de uma etapa.
- Se o usuario pedir "faca tudo", confirme que executara etapas em sequencia, mas ainda registrando checkpoints.
