# Coding Standards

## Objetivo

Garantir consistência, qualidade, segurança, escalabilidade e manutenibilidade em todos os projetos React Native desenvolvidos pela equipe ou por agentes de IA.

---

# Princípios Obrigatórios

Todo código deve seguir:

- SOLID
- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple)
- YAGNI (You Aren't Gonna Need It)
- Clean Code
- Clean Architecture
- Separation of Concerns
- Composition Over Inheritance

---

# Stack Obrigatória

- Expo
- React Native
- TypeScript
- NativeWind
- Shadcn UI
- Zod

---

# TypeScript

Configuração obrigatória:

```json
{
  "extends": "expo/tsconfig.base",
  "compilerOptions": {
    "strict": true,
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

---

## Proibido

```ts
any;
```

```ts
// @ts-ignore
```

```ts
// @ts-nocheck
```

---

## Permitido

```ts
unknown;
```

```ts
Record<string, unknown>;
```

```ts
Partial<T>;
```

```ts
Pick<T>;
```

```ts
Omit<T>;
```

---

# Importações

Sempre utilizar aliases.

Correto:

```ts
import { Button } from "@/components/ui/Button";
import { useAuth } from "@/hooks/useAuth";
```

Incorreto:

```ts
import { Button } from "../../../../components/ui/Button";
```

---

# Padrão de Funções

## Regra Principal

Utilizar Function Declaration.

Preferir:

```ts
function calculateTotal(price: number, quantity: number): number {
  return price * quantity;
}
```

Evitar:

```ts
const calculateTotal = (price: number, quantity: number): number => {
  return price * quantity;
};
```

---

# Componentes React

Sempre utilizar Function Declaration.

Correto:

```tsx
interface ButtonProps {
  title: string;
}

export function Button({ title }: ButtonProps) {
  return (
    <TouchableOpacity>
      <Text>{title}</Text>
    </TouchableOpacity>
  );
}
```

Incorreto:

```tsx
export const Button = ({ title }: ButtonProps) => {
  return (
    <TouchableOpacity>
      <Text>{title}</Text>
    </TouchableOpacity>
  );
};
```

---

# Hooks

Correto:

```ts
export function useAuth() {
  function login() {}

  function logout() {}

  return {
    login,
    logout,
  };
}
```

---

# Services

Correto:

```ts
export async function getUserById(id: string) {
  return api.get(`/users/${id}`);
}
```

---

# Helpers

Correto:

```ts
export function formatCurrency(value: number): string {
  return value.toLocaleString("pt-BR");
}
```

---

# Callbacks

Arrow Functions permitidas apenas para:

```ts
items.map((item) => item.id);

items.filter((item) => item.active);

items.reduce((acc, item) => acc + item.value, 0);
```

ou

```ts
setState((prev) => ({
  ...prev,
}));
```

---

# Convenções de Nomeação

## Componentes

PascalCase

```text
Button.tsx
Input.tsx
UserCard.tsx
ProfileScreen.tsx
```

---

## Hooks

camelCase iniciando com use

```text
useAuth.ts
useTheme.ts
useUser.ts
```

---

## Services

camelCase

```text
authService.ts
userService.ts
paymentService.ts
```

---

## Schemas

PascalCase + Schema

```text
LoginSchema
UserSchema
RegisterSchema
```

---

## Types

PascalCase

```ts
type User = {};

interface UserProps {}
```

---

# Estrutura Obrigatória

```text
src/
├── app/
│   ├── screens/
│   ├── navigation/
│   └── routes/
│
├── components/
│   ├── ui/
│   ├── forms/
│   └── layouts/
│
├── hooks/
│
├── services/
│   ├── api/
│   ├── auth/
│   └── storage/
│
├── assets/
│
├── schemas/
│
├── types/
│
├── constants/
│
├── utils/
│
├── lib/
│
└── theme/
```

Nenhuma feature deve criar estruturas paralelas.

---

# Componentização

Todo componente deve possuir tipagem explícita.

## Button

```tsx
interface ButtonProps extends TouchableOpacityProps {
  title: string;
  loading?: boolean;
}
```

---

## Input

```tsx
interface InputProps extends TextInputProps {
  error?: string;
}
```

---

## Text

```tsx
interface TextProps extends RNTextProps {
  children: React.ReactNode;
}
```

---

# Responsabilidade Única

Cada componente deve ter apenas uma responsabilidade.

Errado:

```text
LoginScreen
├─ formulário
├─ chamada API
├─ autenticação
├─ persistência
├─ validação
```

Correto:

```text
LoginScreen
 ├─ LoginForm
 ├─ useLogin
 ├─ authService
 └─ LoginSchema
```

---

# Estado

Ordem de preferência:

1. useState
2. useReducer
3. Context API
4. Zustand

Evitar Context API para estados complexos.

---

# Validação

Obrigatório utilizar Zod.

Exemplo:

```ts
const LoginSchema = z.object({
  email: z.email(),
  password: z.string().min(8),
});
```

Nenhum dado do usuário deve ser confiado.

---

# Serviços

Nenhuma chamada de API dentro de componentes.

Errado:

```tsx
useEffect(() => {
  axios.get("/users");
}, []);
```

Correto:

```tsx
useEffect(() => {
  userService.getUsers();
}, []);
```

---

# Estilização

Obrigatório:

- NativeWind
- Theme Global

Proibido:

```tsx
style={{
  marginTop: 15,
  backgroundColor: "#ff0000",
}}
```

Correto:

```tsx
className = "mt-4 bg-primary";
```

---

# Theme

Obrigatório:

```text
src/theme/
├── colors.ts
├── spacing.ts
├── typography.ts
├── radius.ts
└── index.ts
```

Nunca utilizar valores mágicos espalhados pelo código.

---

# Segurança

Proibido:

```ts
const apiKey = "123456";
```

```ts
const token = "abcdef";
```

Utilizar:

```ts
process.env.EXPO_PUBLIC_API_URL;
```

---

# Armazenamento Seguro

Utilizar:

```ts
expo - secure - store;
```

Proibido:

```ts
AsyncStorage;
```

para:

- JWT
- Refresh Token
- Dados sensíveis

---

# Tratamento de Erros

Sempre tratar exceções.

```ts
try {
  await login();
} catch (error) {
  handleError(error);
}
```

Nunca ignorar erros.

---

# Logging

Permitido apenas em desenvolvimento.

```ts
if (__DEV__) {
  console.log(data);
}
```

Nunca registrar:

- Senhas
- Tokens
- Dados bancários
- Dados pessoais sensíveis

---

# Performance

Utilizar quando necessário:

```ts
React.memo;
useMemo;
useCallback;
```

Evitar:

- Re-renderizações desnecessárias
- Loops pesados na renderização
- Objetos inline em props

---

# Testes

Obrigatório testar:

- Services
- Hooks
- Schemas
- Regras de negócio

Prioridade:

1. Unit Tests
2. Integration Tests
3. E2E Tests

---

# Documentação

Toda feature deve conter:

- Descrição
- Fluxo
- Dependências
- Limitações

---

# Critérios de Reprovação

Reprovar automaticamente se houver:

✗ any

✗ lógica de negócio na UI

✗ arrow function para componentes

✗ arrow function para hooks

✗ arrow function para services

✗ imports relativos excessivos

✗ ausência de tipagem

✗ ausência de tratamento de erros

✗ ausência de validação Zod

✗ secrets hardcoded

✗ duplicação de código

✗ violação do SOLID

✗ ausência de documentação

✗ armazenamento inseguro de credenciais

✗ uso inadequado de AsyncStorage

✗ código fora da arquitetura definida
