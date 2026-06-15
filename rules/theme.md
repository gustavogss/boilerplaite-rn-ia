# Theme Standards

## Objetivo

Garantir consistência visual, suporte a Light Mode e Dark Mode e centralização de todas as definições visuais da aplicação.

Todo projeto deve possuir um sistema de temas global.

---

# Regra Principal

Toda aplicação deve suportar:

✓ Light Theme

✓ Dark Theme

✓ Detecção automática do sistema

✓ Troca manual pelo usuário

---

# Estrutura Obrigatória

```text
src/
└── theme/
    ├── colors.ts
    ├── spacing.ts
    ├── radius.ts
    ├── typography.ts
    ├── shadows.ts
    ├── theme-provider.tsx
    ├── use-theme.ts
    └── index.ts
```

---

# Provider Global

Obrigatório.

```tsx
export function ThemeProvider({ children }: ThemeProviderProps) {
  return <ThemeContext.Provider>{children}</ThemeContext.Provider>;
}
```

---

# Hook Global

Obrigatório.

```tsx
export function useTheme() {
  return {
    theme,
    setTheme,
    toggleTheme,
  };
}
```

---

# Temas Permitidos

```ts
export type ThemeMode = "light" | "dark" | "system";
```

---

# Persistência

Salvar preferência do usuário.

Utilizar:

```text
AsyncStorage
```

Exemplo:

```ts
theme = "light";
theme = "dark";
theme = "system";
```

---

# Detecção Automática

Utilizar:

```tsx
useColorScheme();
```

Quando o usuário selecionar:

```text
system
```

---

# Tela de Configurações

Toda aplicação deve possuir:

```text
Configurações
 └── Aparência
      ├── Claro
      ├── Escuro
      └── Sistema
```

---

# Cores

Todas as cores devem ser definidas no tema.

Exemplo:

```ts
export const lightColors = {
  background: "#FFFFFF",
  foreground: "#09090B",
  primary: "#2563EB",
  card: "#FFFFFF",
  border: "#E4E4E7",
};
```

```ts
export const darkColors = {
  background: "#09090B",
  foreground: "#FAFAFA",
  primary: "#3B82F6",
  card: "#18181B",
  border: "#27272A",
};
```

---

# Proibido

```tsx
className = "bg-white";
```

```tsx
className = "text-black";
```

```tsx
style={{
  backgroundColor: "#FFF"
}}
```

---

# Permitido

```tsx
className = "bg-background";
```

```tsx
className = "text-foreground";
```

```tsx
className = "border-border";
```

```tsx
className = "bg-card";
```

---

# NativeWind

Configurar tokens:

```js
colors: {
  background: "var(--background)",
  foreground: "var(--foreground)",
  primary: "var(--primary)",
  card: "var(--card)",
  border: "var(--border)",
}
```

---

# Shadcn

Todos os componentes devem consumir:

```text
Theme Provider
```

Nunca utilizar cores fixas.

---

# Splash Screen

Durante inicialização:

1. Carregar tema salvo.
2. Aplicar tema.
3. Renderizar aplicação.

---

# Componentes

Todo componente deve ser compatível com:

```text
Light Theme
Dark Theme
```

Obrigatório testar ambos.

---

# Acessibilidade

Garantir:

✓ Contraste adequado

✓ Legibilidade

✓ Estados visuais claros

✓ Compatibilidade com acessibilidade do sistema

---

# Testes

Validar:

✓ Light Mode

✓ Dark Mode

✓ Troca manual

✓ Persistência

✓ Modo sistema

---

# Critérios de Reprovação

✗ Cores hardcoded

✗ Ausência de Dark Mode

✗ Ausência de Light Mode

✗ Sem Theme Provider

✗ Sem persistência

✗ Sem suporte ao modo sistema

✗ Componentes incompatíveis com tema

✗ Uso de bg-white

✗ Uso de text-black

✗ Uso de cores fixas fora do tema

---

# Regra Suprema

Nenhuma cor pode ser utilizada diretamente na UI.

Toda cor deve ser consumida através do sistema global de temas.
