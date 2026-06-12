# 03-🔨-CONSTRUIR

Execute somente o plano aprovado.

Esta e a unica etapa que implementa codigo por padrao.

## Entrada esperada

```text
Plano aprovado:
[arquivos afetados, estrategia, ordem de execucao e validacao planejada]
```

## Regras de execucao

- Nao crie escopo novo.
- Nao refatore fora do combinado.
- Nao altere arquivos fora da missao.
- Preserve alteracoes existentes do usuario.
- Siga a ordem do plano, salvo bloqueio tecnico real.
- Se precisar mudar o plano, pare e explique o motivo antes de continuar.

## Processo

1. Confirme o plano aprovado.
2. Leia os arquivos citados no plano.
3. Verifique alteracoes locais antes de editar.
4. Implemente em passos pequenos.
5. Mantenha nomes claros e funcoes pequenas.
6. Valide inputs e erros.
7. Preserve seguranca de tenant quando aplicavel.
8. Rode a validacao planejada quando a implementacao terminar.
9. Pare com resumo tecnico e resultado dos testes.

## Padrao de codigo

Priorize:

- codigo simples
- responsabilidades separadas
- early returns quando reduzem complexidade
- erros explicitos
- duplicacao real removida
- comentarios apenas para explicar o porque

Evite:

- abstracoes preventivas
- funcoes grandes
- nomes genericos como `data`, `obj`, `res`, `x`
- `try/catch` que silencia erro
- dependencias novas desnecessarias

## Seguranca obrigatoria

Se envolver dados de usuario, empresa, cliente, lead, proposta ou recurso privado:

- nunca confie apenas no `id`
- filtre tambem por `userId`, `companyId` ou escopo equivalente
- valide entrada no limite da aplicacao
- trate erro de permissao de forma explicita
- nao exponha segredos em logs, erros ou resposta

## Saida obrigatoria

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

## Se nao houver testes

Declare explicitamente:

```text
Nao encontrei testes automatizados disponiveis para esta area.
```

Mesmo assim, rode lint/build quando existirem e faca verificacao manual proporcional.
