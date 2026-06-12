# 04-🧪-TESTAR

Valide a entrega.

Procure bugs, regressoes, falhas de regra de negocio, falhas de UX, falhas de seguranca e inconsistencias tecnicas.

Nao implemente correcao nesta etapa, salvo se o usuario pedir explicitamente.

## Entrada esperada

```text
Entrega para validar:
[objetivo, plano, arquivos alterados, diff ou resumo da implementacao]
```

## Processo

1. Leia objetivo, criterios de aceite e plano.
2. Leia os arquivos alterados e areas afetadas.
3. Rode testes disponiveis.
4. Rode build/lint quando existirem.
5. Verifique manualmente regras de negocio criticas.
6. Revise seguranca, UX e consistencia tecnica.
7. Classifique achados por severidade.
8. Pare e peca aprovacao para corrigir ou entregar.

## Checklist de validacao

### Regra de negocio

- O comportamento atende aos criterios de aceite?
- Algum fluxo importante ficou sem cobertura?
- Existe caso limite obvio ignorado?

### Regressao

- A mudanca quebra fluxo existente?
- O contrato de API, componente ou funcao mudou sem plano?
- Estados vazios, loading e erro continuam funcionando?

### Seguranca

- Inputs sao validados?
- Existe risco de IDOR?
- Queries respeitam `userId`, `companyId` ou escopo equivalente?
- Algum segredo aparece em logs, mensagens ou arquivos?

### UX

- O usuario entende o que aconteceu?
- Erros sao claros?
- Estados vazios orientam proximo passo?
- A interface continua acessivel e responsiva quando aplicavel?

### Tecnico

- Codigo segue o plano?
- Nomes sao claros?
- Funcoes continuam pequenas?
- Nao houve dependencia desnecessaria?
- Nao houve refatoracao fora da missao?

## Saida obrigatoria

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

## Severidade

- `Bloqueante`: impede entrega ou cria risco grave.
- `Alta`: bug relevante, regressao, seguranca ou perda de dados.
- `Media`: problema real com workaround.
- `Baixa`: melhoria pequena, sem impacto critico.

## Se nao houver testes

Declare:

```text
Nao encontrei testes automatizados disponiveis.
```

Depois registre quais verificacoes manuais foram feitas.
