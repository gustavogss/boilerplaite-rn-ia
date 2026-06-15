# Testing Standards

## Objetivo

Garantir qualidade, confiabilidade, segurança e estabilidade da aplicação através de testes automatizados.

Nenhuma funcionalidade crítica pode ser considerada concluída sem cobertura adequada de testes.

---

# Pirâmide de Testes

Prioridade:

```text
E2E
 ▲
 │
Integration
 ▲
 │
Unit
```

Distribuição recomendada:

- 70% Unit Tests
- 20% Integration Tests
- 10% E2E Tests

---

# Ferramentas

## Unit Testing

Utilizar:

```text
Jest
```

---

## Component Testing

Utilizar:

```text
React Native Testing Library
```

---

## E2E

Utilizar:

```text
Detox
```

ou

```text
Maestro
```

---

# Cobertura Mínima

Meta mínima:

```text
80%
```

Cobertura obrigatória para:

- Services
- Hooks
- Schemas
- Regras de negócio
- Funções utilitárias

---

# O que Deve Ser Testado

## Services

Obrigatório.

Exemplo:

```ts
authService;
userService;
paymentService;
notificationService;
```

Testar:

- sucesso
- falha
- timeout
- respostas inválidas

---

## Hooks

Obrigatório.

Exemplo:

```ts
useAuth;
useTheme;
useUser;
```

Testar:

- estado inicial
- atualizações de estado
- comportamento esperado
- cenários de erro

---

## Schemas Zod

Obrigatório.

Exemplo:

```ts
LoginSchema;
RegisterSchema;
ProfileSchema;
```

Testar:

- dados válidos
- dados inválidos
- campos obrigatórios
- limites mínimos e máximos

---

## Utils

Obrigatório.

Exemplo:

```ts
formatCurrency;
formatDate;
calculateTotal;
```

---

## Regras de Negócio

Obrigatório.

Exemplo:

```ts
cálculo de parcelas
cálculo de juros
regras de cashback
regras de assinatura
```

Esses testes possuem prioridade máxima.

---

# Componentes

Testar:

- renderização
- props
- estados
- interação do usuário

Exemplo:

```tsx
Button;
Input;
Modal;
Card;
```

---

# O que NÃO Testar

Evitar testar:

- implementação interna de bibliotecas
- NativeWind
- Shadcn
- React Native
- Expo

Testar comportamento, não implementação.

---

# Estrutura de Testes

```text
src/
├── components/
│
├── hooks/
│
├── services/
│
└── tests/
    ├── unit/
    ├── integration/
    ├── e2e/
    ├── fixtures/
    └── mocks/
```

---

# Nomenclatura

Utilizar:

```text
Button.test.tsx
useAuth.test.ts
authService.test.ts
```

---

# Padrão AAA

Todos os testes devem seguir:

```text
Arrange
Act
Assert
```

Exemplo:

```ts
describe("calculateTotal", () => {
  it("should return correct total", () => {
    // Arrange
    const price = 10;
    const quantity = 2;

    // Act
    const result = calculateTotal(price, quantity);

    // Assert
    expect(result).toBe(20);
  });
});
```

---

# Mocking

Mockar apenas dependências externas.

Exemplo:

```ts
API
Banco de Dados
Storage
Serviços externos
```

Evitar mock excessivo.

---

# Integração

Testar integração entre:

```text
Screen → Hook
Hook → Service
Service → API
Form → Schema
```

---

# E2E

Fluxos obrigatórios:

## Autenticação

```text
Login
Logout
Recuperação de senha
```

---

## Navegação

```text
Tela inicial
Fluxos principais
Rotas protegidas
```

---

## Funcionalidades Críticas

```text
Pagamento
Assinatura
Investimentos
Transferências
Cadastro
```

---

# Segurança

Testar:

- Inputs inválidos
- Payloads maliciosos
- Falhas de autenticação
- Falhas de autorização
- Dados obrigatórios ausentes

---

# Performance

Validar:

- Renderizações excessivas
- Loops desnecessários
- Consultas duplicadas
- Requests redundantes

---

# Critérios de Aprovação

Uma feature somente pode ser aprovada quando:

✓ Todos os testes passarem

✓ Cobertura mínima atingida

✓ Nenhum teste falhando

✓ Nenhum teste ignorado

✓ Nenhum TODO pendente

✓ Casos de erro testados

✓ Casos de sucesso testados

✓ Casos de borda testados

---

# Critérios de Reprovação

Reprovar automaticamente quando houver:

✗ Testes ausentes

✗ Cobertura abaixo de 80%

✗ Testes comentados

✗ Testes ignorados

✗ TODO em testes críticos

✗ Falta de testes para Services

✗ Falta de testes para Hooks

✗ Falta de testes para Schemas

✗ Falta de testes para regras de negócio

✗ Dependência de ambiente externo para execução

✗ Testes não determinísticos

✗ Uso excessivo de mocks

---

# Responsabilidades dos Agentes

Frontend Agent

- Criar testes de componentes
- Criar testes de hooks

Backend Agent

- Criar testes de services
- Criar testes de regras de negócio

QA Agent

- Criar cenários de integração
- Criar testes E2E

Security Agent

- Criar testes de segurança

Reviewer Agent

- Validar qualidade dos testes

DevSecOps Agent

- Garantir execução automática dos testes no pipeline CI/CD

Nenhum Pull Request pode ser aprovado sem a validação do QA Agent e Reviewer Agent.
