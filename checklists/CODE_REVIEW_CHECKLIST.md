# 📋 Code Review Checklist

## Pre-Review Preparation

### Code Organization
- [ ] Código segue a estrutura de pastas do projeto
- [ ] Arquivos organizados logicamente
- [ ] Sem arquivos desnecessários adicionados
- [ ] Imports/requires organizados e sem circulares

### Naming & Readability
- [ ] Variáveis com nomes descritivos
- [ ] Funções/classes com nomes claros
- [ ] Constantes em UPPER_CASE
- [ ] Evita abreviações confusas
- [ ] Sem caracteres especiais em nomes

### Code Quality

#### Functions & Methods
- [ ] Funções fazem UMA coisa
- [ ] Máximo 30 linhas por função
- [ ] Máximo 3 parâmetros (use objetos se necessário)
- [ ] Sem side effects inesperados
- [ ] Retornam consistentemente

#### Variables & Constants
- [ ] Usa `const` por padrão
- [ ] `let` apenas se necessário reatribuir
- [ ] Não usa `var`
- [ ] Sem números mágicos
- [ ] Sem variáveis globais desnecessárias

#### DRY Principle
- [ ] Sem duplicação de código
- [ ] Métodos/funções reutilizáveis
- [ ] Lógica centralizada
- [ ] Configurações externalizadas

### Error Handling
- [ ] Try-catch para operações arriscadas
- [ ] Mensagens de erro descritivas
- [ ] Sem silenciar erros
- [ ] Logs adequados
- [ ] Null/undefined checks

### Testing
- [ ] Testes inclusos para novas features
- [ ] Testes para edge cases
- [ ] Coverage > 80%
- [ ] Testes passando (CI/CD)
- [ ] Sem testes marcados como skip/ignore

### Performance
- [ ] Sem N+1 queries
- [ ] Loop efficiency considerado
- [ ] Cache implementado se necessário
- [ ] Sem operações bloqueantes
- [ ] Algoritmo apropriado para o problema

### Security
- [ ] Sem hardcoded passwords/keys
- [ ] Entrada validada
- [ ] Sanitização de dados
- [ ] SQL injection prevenido
- [ ] XSS prevention

### Documentation
- [ ] README atualizado se necessário
- [ ] Code comments explicam o "porquê"
- [ ] JSDoc/comentários de função
- [ ] README de features complexas
- [ ] Changelog atualizado

### Dependencies
- [ ] Sem dependências desnecessárias
- [ ] Versões pinadas apropriadamente
- [ ] Vulnerabilidades verificadas
- [ ] Licenses compatíveis
- [ ] Package.json e lock file sincronizados

### Git Practices
- [ ] Commits atômicos e semânticos
- [ ] Mensagens de commit descritivas
- [ ] Sem merge commits desnecessários
- [ ] Histórico limpo
- [ ] Branch atualizado com main/develop

### Accessibility & UI/UX
- [ ] Código a11y considerado
- [ ] Labels e aria attributes
- [ ] Testes de contraste
- [ ] Responsive design
- [ ] Sem hardcoded dimensions

## Red Flags (Rejeitar se presente)

```
🚫 SECURITY
- Credenciais em código
- SQL injection vulnerability
- XSS vulnerability
- Sem validação de entrada

🚫 PERFORMANCE
- N+1 queries
- Loops aninhados desnecessários
- Operações bloqueantes
- Memory leaks

🚫 CODE QUALITY
- Funções > 100 linhas
- Duplicação óbvia
- Sem testes críticos
- Comentários enganosos

🚫 BEST PRACTICES
- Todas as funções têm side effects
- Código morto/comentado
- Magic numbers
- Variáveis globais
```

## Nice-to-Have

✓ Type hints/JSDoc  
✓ Performance optimizations  
✓ Logging estratégico  
✓ Error boundaries (React)  
✓ Mocking estratégico  

## Feedback Template

```markdown
### ✅ Strengths
- [Aspecto positivo 1]
- [Aspecto positivo 2]

### 🔧 Improvements
- [Sugestão 1]: Explique o porquê
- [Sugestão 2]: Forneça alternativa

### ❓ Questions
- Qual é o objetivo aqui?
- Considerou alternativa X?

### 🎯 Blocking Issues
- [Problema crítico]: Necessário corrigir

Approved / Request Changes / Comment
```

## Reviewing Different Code Types

### API Endpoints
- [ ] HTTP method apropriado (GET, POST, etc)
- [ ] Status codes corretos
- [ ] Erro handling completo
- [ ] Rate limiting considerado
- [ ] Documentação (OpenAPI/Swagger)

### Database Queries
- [ ] Usa índices apropriados
- [ ] JOIN syntax correto
- [ ] N+1 queries prevenido
- [ ] Query otimizada
- [ ] Migrations versionadas

### React Components
- [ ] Hooks usados corretamente
- [ ] Props validadas
- [ ] Re-renders otimizados
- [ ] Memory leaks prevenidos
- [ ] Testes de componente

### State Management
- [ ] Ações/reducers são puras
- [ ] Estado não é mutado
- [ ] Seletores memoizados
- [ ] Sem lógica complexa em Redux
- [ ] Combinação correta de providers

---

**Tempo médio de review**: 15-30 min  
**Objetivo**: Código de produção de qualidade

