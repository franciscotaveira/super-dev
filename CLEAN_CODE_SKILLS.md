# 🎯 Clean Code & Developer Skills Guide

Uma compilação completa de princípios, práticas e habilidades essenciais para desenvolvedores escreverem código limpo e profissional.

## 📚 Índice

1. [Princípios Fundamentais de Clean Code](#princípios-fundamentais)
2. [Habilidades Essenciais do Desenvolvedor](#habilidades-essenciais)
3. [Boas Práticas de Codificação](#boas-práticas)
4. [Arquitetura e Design](#arquitetura-e-design)
5. [Testes e Qualidade](#testes-e-qualidade)
6. [Colaboração e Soft Skills](#colaboração-e-soft-skills)
7. [Recursos e Referências](#recursos)

---

## Princípios Fundamentais

### 1. Nomenclatura Clara
```
❌ BAD
const d = new Date();
const yyyymmdstr = moment(d).format('YYYY/MM/DD');

✅ GOOD
const currentDate = new Date();
const formattedCurrentDate = moment(currentDate).format('YYYY/MM/DD');
```

**Práticas:**
- Use nomes descritivos e pronouncáveis
- Nomes devem revelar intenção
- Use nomes pesquisáveis
- Evite desinformação
- Nomes de classes: substantivos
- Nomes de métodos: verbos
- Uma palavra por conceito

### 2. Funções Pequenas e Focadas

```javascript
// ❌ BAD - Função faz muitas coisas
function getUserData(userId) {
  const user = database.find(userId);
  const validated = validateUser(user);
  const permissions = getPermissions(user);
  const formatted = formatUserData(user);
  const audit = logAudit(user);
  sendNotification(user);
  return { user, validated, permissions, formatted, audit };
}

// ✅ GOOD - Funções pequenas e específicas
function getUserData(userId) {
  return database.find(userId);
}

function validateAndEnrichUser(user) {
  const validated = validateUser(user);
  const permissions = getPermissions(user);
  return { user, validated, permissions };
}
```

**Regras:**
- Função deve fazer UMA coisa bem
- Deve fazer bem E nada mais
- Máximo 20-30 linhas
- Máximo 3 parâmetros
- Sem side effects

### 3. Tratamento de Erros

```javascript
// ❌ BAD
function divide(a, b) {
  return a / b;
}

// ✅ GOOD
function divide(a, b) {
  if (b === 0) {
    throw new Error('Divisor cannot be zero');
  }
  return a / b;
}

// ✅ BETTER
function safelyDivide(a, b) {
  try {
    if (!isNumber(a) || !isNumber(b)) {
      throw new TypeError('Both arguments must be numbers');
    }
    if (b === 0) {
      throw new Error('Division by zero');
    }
    return a / b;
  } catch (error) {
    logger.error('Division error:', error);
    return null;
  }
}
```

### 4. DRY - Don't Repeat Yourself

```javascript
// ❌ BAD - Código repetido
function getUserById(id) {
  if (!id) throw new Error('ID is required');
  const user = database.find(id);
  if (!user) throw new Error('User not found');
  return user;
}

function getPostById(id) {
  if (!id) throw new Error('ID is required');
  const post = database.find(id);
  if (!post) throw new Error('Post not found');
  return post;
}

// ✅ GOOD - Abstração reutilizável
function getEntityById(collection, id, entityName) {
  if (!id) throw new Error('ID is required');
  const entity = collection.find(id);
  if (!entity) throw new Error(`${entityName} not found`);
  return entity;
}

const getUserById = (id) => getEntityById(users, id, 'User');
const getPostById = (id) => getEntityById(posts, id, 'Post');
```

### 5. SOLID Principles

#### S - Single Responsibility Principle
```javascript
// ❌ BAD - Classe com múltiplas responsabilidades
class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }
  
  save() { /* salvar no DB */ }
  sendEmail() { /* enviar email */ }
  generateReport() { /* gerar relatório */ }
}

// ✅ GOOD - Separação de responsabilidades
class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }
}

class UserRepository {
  save(user) { /* salvar no DB */ }
}

class UserEmailService {
  send(user, message) { /* enviar email */ }
}

class UserReportGenerator {
  generate(user) { /* gerar relatório */ }
}
```

#### O - Open/Closed Principle
```javascript
// ❌ BAD - Precisa modificar para adicionar novos tipos
function calculateDiscount(customer, amount) {
  if (customer.type === 'gold') {
    return amount * 0.2;
  } else if (customer.type === 'silver') {
    return amount * 0.1;
  }
  return 0;
}

// ✅ GOOD - Aberto para extensão, fechado para modificação
class DiscountStrategy {
  calculate(amount) { }
}

class GoldDiscount extends DiscountStrategy {
  calculate(amount) { return amount * 0.2; }
}

class SilverDiscount extends DiscountStrategy {
  calculate(amount) { return amount * 0.1; }
}

function applyDiscount(customer, amount) {
  return customer.discountStrategy.calculate(amount);
}
```

#### L - Liskov Substitution Principle
```javascript
// ❌ BAD
class Bird {
  fly() { }
}

class Penguin extends Bird {
  fly() {
    throw new Error('Penguins cannot fly');
  }
}

// ✅ GOOD
class Bird { }

class FlyingBird extends Bird {
  fly() { }
}

class NonFlyingBird extends Bird { }

class Penguin extends NonFlyingBird { }
```

#### I - Interface Segregation Principle
```javascript
// ❌ BAD - Interface gorda
interface Animal {
  eat(): void;
  fly(): void;
  swim(): void;
}

// ✅ GOOD - Interfaces específicas
interface Eater {
  eat(): void;
}

interface Flyer {
  fly(): void;
}

interface Swimmer {
  swim(): void;
}

class Dog implements Eater, Swimmer { }
class Eagle implements Eater, Flyer { }
```

#### D - Dependency Inversion Principle
```javascript
// ❌ BAD - Dependência direta
class EmailSender {
  send(email) { }
}

class UserService {
  constructor() {
    this.emailSender = new EmailSender();
  }
}

// ✅ GOOD - Inversão de dependência
interface MessageSender {
  send(message): void;
}

class UserService {
  constructor(messageSender: MessageSender) {
    this.messageSender = messageSender;
  }
}
```

---

## Habilidades Essenciais

### 1. **Estruturas de Dados**
- Arrays e Listas
- Objetos e Hash Maps
- Pilhas e Filas
- Árvores e Grafos
- Heaps
- Tries

### 2. **Algoritmos**
- Busca (Linear, Binária)
- Ordenação (QuickSort, MergeSort, etc)
- Recursão
- Programação Dinâmica
- Greedy Algorithms
- Busca em Grafos (BFS, DFS)

### 3. **Complexidade**
- Notação Big-O
- Análise de Tempo
- Análise de Espaço
- Otimização

```javascript
// Exemplos de complexidade
O(1)     - Acesso a array por índice
O(n)     - Busca linear
O(log n) - Busca binária
O(n²)    - Bubble sort
O(n log n) - Merge sort
O(2ⁿ)    - Fibonacci recursivo
```

### 4. **Design Patterns**

| Pattern | Uso | Exemplo |
|---------|-----|---------|
| Singleton | Uma única instância | Logger, Database |
| Factory | Criar objetos | User, Post |
| Observer | Notificações | Event Emitters |
| Strategy | Algoritmos intercambiáveis | Pagamento |
| Decorator | Adicionar comportamento | Cache |
| Middleware | Processar requisições | Express |

### 5. **Versionamento (Git)**
- Commits semânticos
- Branches e PRs
- Rebase vs Merge
- Squash commits
- Cherry-pick

```bash
# Commits semânticos
feat: adicionar nova feature
fix: corrigir bug
docs: documentação
style: formatação
refactor: refatoração
perf: performance
test: testes
chore: tarefas
```

### 6. **Banco de Dados**
- SQL (SELECT, JOIN, INDEX)
- Normalização
- N+1 Queries
- Transações
- NoSQL (quando usar)

### 7. **APIs & REST**
- HTTP Methods (GET, POST, PUT, DELETE)
- Status Codes (200, 400, 404, 500)
- Autenticação (JWT, OAuth)
- Rate Limiting
- Versionamento

---

## Boas Práticas

### 1. Code Comments
```javascript
// ❌ BAD - Óbvio
const age = 25; // set age to 25

// ✅ GOOD - Explica o porquê
const maxRetries = 3; // Allow 3 retries due to network latency issues

// ✅ TODO/FIXME
// TODO: Implement pagination for large datasets
// FIXME: Performance issue with large arrays
```

### 2. Variáveis & Constantes
```javascript
// Use const por padrão
const MAX_USERS = 100;
const user = { name: 'John' };

// Use let se precisa reatribuir
let counter = 0;
for (let i = 0; i < 10; i++) {
  counter += i;
}

// Evite var
var oldStyle = 'avoid'; // ❌
```

### 3. Evite Números Mágicos
```javascript
// ❌ BAD
if (age > 18 && age < 65) {
  // ...
}

// ✅ GOOD
const LEGAL_AGE = 18;
const RETIREMENT_AGE = 65;
if (age > LEGAL_AGE && age < RETIREMENT_AGE) {
  // ...
}
```

### 4. Early Returns
```javascript
// ❌ BAD - Muitos níveis de indentação
function processUser(user) {
  if (user) {
    if (user.isActive) {
      if (user.hasPermission) {
        return user.data;
      }
    }
  }
  return null;
}

// ✅ GOOD - Early returns
function processUser(user) {
  if (!user) return null;
  if (!user.isActive) return null;
  if (!user.hasPermission) return null;
  return user.data;
}
```

### 5. Formatting & Linting
```javascript
// Use formatters
// - Prettier (formatting)
// - ESLint (code quality)
// - EditorConfig (consistency)

// .eslintrc.json
{
  "extends": "eslint:recommended",
  "env": {
    "browser": true,
    "node": true,
    "es2021": true
  },
  "rules": {
    "no-var": "error",
    "prefer-const": "error",
    "eqeqeq": "error"
  }
}
```

---

## Arquitetura e Design

### 1. Arquitetura em Camadas
```
┌─────────────────────┐
│   Presentation      │ UI/Controllers
├─────────────────────┤
│   Application       │ Use Cases/Services
├─────────────────────┤
│   Domain            │ Business Logic
├─────────────────────┤
│   Infrastructure    │ Database/External Services
└─────────────────────┘
```

### 2. MVC (Model-View-Controller)
- **Model**: Dados e lógica de negócio
- **View**: Apresentação
- **Controller**: Coordena Model e View

### 3. Clean Architecture
- Independente de Framework
- Testável
- Independente de UI
- Independente de Banco de Dados
- Independente de Agências Externas

### 4. Microserviços
- Serviços independentes
- Comunicação via APIs
- Dados descentralizados
- Deploy independente

---

## Testes e Qualidade

### 1. Tipos de Testes
```
       ▲
       │     UI Tests
       │    ┌───────────┐
       │    │ E2E Tests │
       │    └─────┬─────┘
       │     Integration Tests
       │    ┌─────┴─────┐
    Q  │    │  Unit Tests│
    u  │    └───────────┘
    a  │
    l  │
    i  │ Pyramid
    d  │ of
    a  │ Testing
    d  │
    e  │
       │
       └──────────────────►
           Quantidade
```

### 2. Unit Tests
```javascript
// Jest example
describe('Calculator', () => {
  it('should add two numbers correctly', () => {
    const result = add(2, 3);
    expect(result).toBe(5);
  });
});
```

### 3. Test Coverage
```
❌ BAD     - Sem testes (0%)
⚠️  LOW    - Menos de 50%
✓ GOOD    - 70-80%
✓✓ EXCELLENT - Acima de 80%
```

### 4. TDD (Test-Driven Development)
```
1. Red   - Escrever teste que falha
2. Green - Escrever código mínimo para passar
3. Refactor - Melhorar o código
```

### 5. Code Quality Metrics
- **Cyclomatic Complexity**: máximo 10
- **Cognitive Complexity**: máximo 15
- **Lines per Function**: máximo 50
- **Comment Ratio**: 10-20%

---

## Colaboração e Soft Skills

### 1. Code Review
```markdown
✓ Checklist de Code Review:
- [ ] Código segue o style guide
- [ ] Nomes são claros
- [ ] Funções são pequenas
- [ ] Sem código duplicado
- [ ] Tratamento de erros adequado
- [ ] Testes estão inclusos
- [ ] Documentação atualizada
```

### 2. Comunicação
- **Clara**: Explique o "porquê"
- **Empática**: Entenda perspectivas diferentes
- **Documentada**: Deixe evidências
- **Ativa**: Pergunte e escute

### 3. Problem-Solving
1. **Entenda o problema**: Faça perguntas
2. **Quebre em partes**: Divide and conquer
3. **Explore soluções**: Brainstorm alternativas
4. **Implemente**: MVP primeiro
5. **Itere**: Melhore continuamente

### 4. Aprendizado Contínuo
- Leia código de qualidade
- Contribua em open-source
- Participe de code reviews
- Estude design patterns
- Acompanhe tendências
- Pratique regularmente

---

## Recursos

### 📚 Livros Essenciais
- **Clean Code** - Robert C. Martin
- **The Pragmatic Programmer** - Hunt & Thomas
- **Design Patterns** - Gang of Four
- **Refactoring** - Martin Fowler
- **The Software Craftsman** - Sandro Mancuso

### 🎓 Plataformas
- LeetCode (algoritmos)
- HackerRank (problemas)
- Codewars (katas)
- Frontend Masters (cursos)
- Pluralsight (desenvolvimento)

### 🔗 Websites
- MDN Web Docs
- Stack Overflow
- GitHub
- Dev.to
- Medium

### 🛠️ Ferramentas
- Git & GitHub
- VS Code
- ESLint & Prettier
- Jest/Mocha (testes)
- Docker (containerização)

---

## Checklist de Clean Code

Antes de fazer commit, verifique:

- [ ] Nomes são descritivos e claros
- [ ] Funções fazem UMA coisa bem
- [ ] Sem duplicação de código
- [ ] Tratamento de erros adequado
- [ ] Testes inclusos e passando
- [ ] Código formatado
- [ ] Documentação atualizada
- [ ] Sem console.logs ou debug code
- [ ] Performance considerada
- [ ] Segurança revisada

---

## Progresso Pessoal

Acompanhe seu desenvolvimento nestes pilares:

| Pilar | Iniciante | Intermediário | Avançado |
|-------|-----------|---------------|----------|
| **Fundamentos** | Variáveis, funções | Closures, Higher-order | Metaprogramação |
| **Padrões** | Callbacks | Promises, Async | Streams, Generators |
| **Arquitetura** | Scripts | MVC | Clean, Event-driven |
| **Testes** | Ad-hoc | Unit & Integration | TDD, BDD |
| **Performance** | Básico | Profiling | Otimização avançada |

---

**Última atualização**: 2026-06-10  
**Contribuições**: Envie PRs para melhorias!
