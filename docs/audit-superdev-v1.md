# Auditoria SuperDev v1

## O que existia

A versao anterior era composta principalmente por:

- `README.md`
- `SUPER_DEV_COMPLETE.md`
- `CLEAN_CODE_SKILLS.md`
- `docs/01-fundamentals.md`
- `checklists/super-dev-checklist.md`
- `checklists/CODE_REVIEW_CHECKLIST.md`

## Diagnostico

A v1 tinha bons principios, mas funcionava como uma skill monolitica.

Ela misturava:

- definicao de principios
- persona de equipe completa
- analise
- implementacao
- revisao
- testes
- entrega
- conteudo educacional longo

Isso aumentava carga cognitiva e incentivava o agente a fazer varias etapas na mesma chamada.

## Preservar

- Clean Code.
- Nomes claros.
- Funcoes pequenas.
- Tratamento explicito de erro.
- SOLID como referencia, sem dogmatismo.
- Testes e validacao.
- Seguranca contra IDOR.
- Validacao de inputs.
- Escopo por `userId`/`companyId` quando aplicavel.
- Commits semanticos como boa pratica.
- Revisao de performance quando houver risco real.

## Remover ou reduzir

- Persona "equipe completa" como fluxo obrigatorio.
- Linguagem de "elite pipeline" e "mission critical" em excesso.
- Conteudo educacional generico demais para uso diario.
- Checklists longas que competem com a execucao.
- Obrigatoriedade de TDD para qualquer caso, substituida por validacao proporcional.
- Design Patterns como sugestao padrao, substituidos por simplicidade primeiro.
- Refatoracao "sem piedade", substituida por escopo aprovado.

## Decisao de arquitetura

A v2 foi reorganizada em seis skills pequenas:

- `00-🧠-SUPERDEV.md`: governanca.
- `01-💡-IDEIA.md`: objetivo para especificacao.
- `02-📋-PLANO.md`: especificacao para plano.
- `03-🔨-CONSTRUIR.md`: plano para implementacao.
- `04-🧪-TESTAR.md`: validacao.
- `05-📦-ENTREGAR.md`: fechamento.

Tambem foi criado `/ai/context` para promover Context First sem acoplar contexto de um produto especifico dentro das skills.
