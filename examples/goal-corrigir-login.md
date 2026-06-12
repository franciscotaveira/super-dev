# Exemplo: corrigir abandono no login

```text
Use:
00-🧠-SUPERDEV
+
01-💡-IDEIA

GOAL:
Reduzir abandono no login causado por mensagens de erro confusas.
```

## Boa especificacao deve responder

- Quais erros confundem os usuarios?
- O problema esta em credenciais, sessao expirada, rede ou permissao?
- O usuario precisa de recuperacao de senha?
- Como medir reducao de abandono?

## Possiveis criterios de aceite

- Erros de credenciais usam mensagem clara e segura.
- Falhas de rede orientam nova tentativa.
- Sessao expirada explica o que aconteceu.
- Nenhuma mensagem revela se um email existe ou nao, quando isso criar risco.

## Possivel metrica

Reduzir tentativas repetidas de login apos erro em uma semana.
