# 02-📋-PLANO

Transforme uma especificacao aprovada em plano tecnico.

Nao implemente codigo.

Nao altere arquivos.

## Entrada esperada

```text
Especificacao aprovada:
[problema, objetivo, escopo, nao escopo, criterios de aceite e metrica]
```

## Processo

1. Leia a especificacao aprovada.
2. Leia o contexto tecnico disponivel:
   - `/ai/context/architecture.md`
   - `/ai/context/business-rules.md`
   - `/ai/context/decision-log.md`
3. Inspecione o projeto apenas o suficiente para planejar.
4. Liste arquivos provaveis afetados.
5. Defina estrategia de implementacao.
6. Identifique riscos, impactos e validacoes.
7. Defina ordem de execucao.
8. Pare e peca aprovacao.

## Saida obrigatoria

```text
Resumo da especificacao
[objetivo aprovado em 1-3 linhas]

Arquivos afetados
- [arquivo ou area]: [motivo]

Estrategia de implementacao
- [decisao tecnica simples]

Ordem de execucao
1. [passo]
2. [passo]
3. [passo]

Riscos e mitigacoes
- [risco]: [mitigacao]

Impactos
- Negocio: [impacto]
- Tecnico: [impacto]
- UX: [impacto, se houver]
- Seguranca: [impacto, se houver]

Validacao planejada
- [teste, lint, build ou verificacao manual]

Fora do plano
- [o que nao sera feito]

Ponto de parada
Aprove este plano para eu seguir para 03-🔨-CONSTRUIR.
```

## Regras

- Planeje o menor caminho seguro.
- Nao inclua refatoracoes fora do objetivo.
- Nao proponha dependencia nova sem explicar ganho e alternativa.
- Proteja escopo por `userId`/`companyId` quando aplicavel.
- Planeje validacao de input e tratamento de erro.
- Planeje testes proporcionais ao risco.

## Proibido nesta etapa

- editar arquivos
- criar codigo
- criar migracoes
- rodar formatacao que altere arquivos
- expandir escopo sem pedir aprovacao
