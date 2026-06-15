# Shadcn UI Standards

## Objetivo

Garantir que toda interface utilize componentes reutilizáveis baseados em Shadcn UI.

Não criar componentes customizados quando existir equivalente no Shadcn.

---

# Regra Principal

Antes de criar qualquer componente:

1. Verificar se existe no Shadcn.
2. Reutilizar.
3. Extender.
4. Somente então criar novo componente.

---

# Estrutura

```text
src/components/
├── ui/
│   ├── button.tsx
│   ├── input.tsx
│   ├── card.tsx
│   ├── dialog.tsx
│   └── ...
```

---

# Componentes Base

Priorizar:

```text
Button
Input
Textarea
Card
Dialog
Avatar
Badge
Separator
ScrollArea
Sheet
Tabs
Switch
Checkbox
RadioGroup
Select
Skeleton
```

---

# Componentes Customizados

Criar apenas quando:

- Não existir equivalente
- Houver necessidade de negócio

---

# Button

Obrigatório:

```tsx
interface ButtonProps extends TouchableOpacityProps {
  variant?: ButtonVariant;
  size?: ButtonSize;
}
```

---

# Input

Obrigatório:

```tsx
interface InputProps extends TextInputProps {
  error?: string;
}
```

---

# Variantes

Utilizar CVA.

Exemplo:

```ts
default
secondary
outline
ghost
destructive
```

---

# Estados

Todo componente deve suportar:

```text
default
disabled
loading
focused
error
success
```

---

# Acessibilidade

Obrigatório:

```tsx
accessibilityLabel;
accessibilityRole;
accessibilityHint;
```

---

# Tema

Todos os componentes devem consumir:

```text
src/theme
```

Nunca:

```tsx
backgroundColor: "#FFFFFF";
```

---

# Composição

Preferir:

```tsx
<Card>
  <CardHeader />
  <CardContent />
  <CardFooter />
</Card>
```

Evitar componentes monolíticos.

---

# Formulários

Obrigatório:

```text
React Hook Form
+
Zod
```

Estrutura:

```tsx
<Form>
  <FormField />
  <FormLabel />
  <FormControl />
  <FormMessage />
</Form>
```

---

# Reutilização

Antes de criar:

```tsx
UserCard;
ProductCard;
InvestmentCard;
```

avaliar se pode ser:

```tsx
<Card />
```

com composição.

---

# Critérios de Reprovação

✗ Duplicação de componentes

✗ Componente sem tipagem

✗ Componente sem variantes

✗ Componente sem acessibilidade

✗ Componente sem suporte a tema

✗ Componente sem composição

✗ Uso de estilos hardcoded

✗ Ignorar componentes Shadcn existentes

✗ Formulários sem React Hook Form + Zod
