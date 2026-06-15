# React Native Skill

## Objetivo

Implementar aplicações React Native modernas, escaláveis, performáticas, seguras e alinhadas à arquitetura definida pelo projeto.

Esta skill deve ser utilizada por todos os agentes que implementam código React Native.

---

# Stack Obrigatória

- Expo
- React Native
- TypeScript
- NativeWind
- Shadcn UI
- Zod
- React Hook Form

---

# Arquitetura

Seguir obrigatoriamente:

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
│
├── assets/
│
├── schemas/
│
├── theme/
│
├── types/
│
├── utils/
│
└── constants/
```

---

# Componentes

Todo componente deve:

✓ Ser reutilizável

✓ Ser tipado

✓ Ser testável

✓ Possuir responsabilidade única

---

# Exemplo de Componente

```tsx
interface ButtonProps extends TouchableOpacityProps {
  title: string;
}

export function Button({ title, ...props }: ButtonProps) {
  return (
    <TouchableOpacity {...props}>
      <Text>{title}</Text>
    </TouchableOpacity>
  );
}
```

---

# Funções

Utilizar Function Declaration.

Correto:

```ts
function calculateTotal(price: number, quantity: number): number {
  return price * quantity;
}
```

---

# Componentes React

Correto:

```tsx
export function HomeScreen() {
  return <View />;
}
```

Evitar:

```tsx
export const HomeScreen = () => {
  return <View />;
};
```

---

# Hooks

Correto:

```tsx
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

# Navegação

Separar:

```text
screens
navigation
routes
```

Nunca misturar regras de negócio com navegação.

---

# Estado

Prioridade:

```text
useState
↓
useReducer
↓
Context API
↓
Zustand
```

Evitar Context API para estados complexos.

---

# Formulários

Obrigatório:

```text
React Hook Form
+
Zod
```

Exemplo:

```tsx
const form = useForm({
  resolver: zodResolver(LoginSchema),
});
```

---

# Validação

Toda entrada deve utilizar:

```text
Zod
```

Exemplo:

```ts
const LoginSchema = z.object({
  email: z.email(),
  password: z.string().min(8),
});
```

---

# Serviços

Toda integração externa deve estar em:

```text
src/services
```

Exemplo:

```text
authService.ts
userService.ts
paymentService.ts
```

---

# API

Nunca chamar APIs diretamente na UI.

Errado:

```tsx
axios.get("/users");
```

Correto:

```tsx
userService.getUsers();
```

---

# Estilização

Utilizar exclusivamente:

```text
NativeWind
```

Correto:

```tsx
<View className="flex-1 bg-background">
```

Evitar:

```tsx
<View
  style={{
    flex: 1,
  }}
>
```

---

# Tema

Todo componente deve respeitar:

```text
Light Theme
Dark Theme
System Theme
```

Utilizar:

```tsx
bg - background;
text - foreground;
bg - card;
border - border;
```

Nunca:

```tsx
bg - white;
text - black;
```

---

# Listas

Listas pequenas:

```tsx
FlatList;
```

Listas grandes:

```tsx
FlashList;
```

---

# Imagens

Preferência:

```tsx
expo - image;
```

Exemplo:

```tsx
<Image source={avatar} contentFit="cover" />
```

---

# Loading

Toda requisição deve possuir:

```text
loading
success
error
empty
```

---

# Tratamento de Erros

Sempre:

```tsx
try {
} catch (error) {}
```

Nunca ignorar exceções.

---

# Performance

Utilizar quando necessário:

```tsx
React.memo;
useMemo;
useCallback;
```

Evitar:

- Re-renderizações desnecessárias
- Objetos inline
- Funções inline complexas

---

# Acessibilidade

Obrigatório:

```tsx
accessibilityLabel;
accessibilityRole;
accessibilityHint;
```

---

# Segurança

Nunca:

- Expor tokens
- Expor API Keys
- Armazenar JWT em AsyncStorage

Utilizar:

```text
expo-secure-store
```

---

# Testes

Cobertura mínima:

```text
80%
```

Testar:

✓ Components

✓ Hooks

✓ Services

✓ Schemas

✓ Business Rules

---

# Checklist de Implementação

Antes de concluir qualquer feature:

✓ Arquitetura respeitada

✓ Componentes tipados

✓ Sem any

✓ Sem Arrow Functions para componentes

✓ Sem lógica de negócio na UI

✓ Validação com Zod

✓ NativeWind aplicado

✓ Tema global respeitado

✓ Tratamento de erros implementado

✓ Testes criados

✓ Documentação atualizada

---

# Critérios de Reprovação

✗ any

✗ lógica de negócio em screens

✗ API chamada diretamente na UI

✗ ausência de tipagem

✗ ausência de Zod

✗ ausência de testes

✗ ausência de tratamento de erros

✗ estilos inline

✗ cores hardcoded

✗ violação da arquitetura

✗ componente sem reutilização

✗ uso inadequado de AsyncStorage
