# NativeWind Standards

## Objetivo

Garantir consistência visual, escalabilidade e manutenibilidade utilizando NativeWind como solução oficial de estilização.

Todo estilo deve ser implementado utilizando classes NativeWind.

---

# Regra Principal

Utilizar:

```tsx
<View className="flex-1 bg-background">
  <Text className="text-foreground">Olá Mundo</Text>
</View>
```

Evitar:

```tsx
<View
  style={{
    flex: 1,
    backgroundColor: "#fff",
  }}
>
```

---

# Prioridade de Estilização

```text
Theme
↓
Tokens
↓
NativeWind Classes
↓
StyleSheet (exceções)
↓
Inline Styles (proibido)
```

---

# Proibido

```tsx
style={{
  marginTop: 16
}}
```

```tsx
style={[
  styles.container,
  {
    marginTop: 20
  }
]}
```

```tsx
backgroundColor: "#FF0000";
```

---

# Permitido

```tsx
className = "mt-4";
```

```tsx
className = "bg-primary";
```

```tsx
className = "rounded-xl";
```

---

# Design Tokens

Toda cor deve vir do tema.

Nunca:

```tsx
className = "bg-red-500";
```

Preferir:

```tsx
className = "bg-primary";
```

---

# Espaçamentos

Utilizar escala consistente.

Correto:

```tsx
className = "p-4";
className = "m-4";
className = "gap-4";
```

Evitar:

```tsx
className = "p-[13px]";
```

---

# Layout

Utilizar Flexbox.

```tsx
className = "flex-row items-center justify-between";
```

---

# Responsividade

Utilizar:

```tsx
useWindowDimensions();
```

Evitar valores fixos.

---

# Dark Mode

Obrigatório.

Exemplo:

```tsx
className = "bg-background text-foreground";
```

Nunca:

```tsx
className = "bg-white text-black";
```

---

# Animações

Preferência:

```text
react-native-reanimated
```

---

# Tipografia

Nunca utilizar:

```tsx
text-[17px]
```

Utilizar tokens.

```tsx
text - base;
text - lg;
text - xl;
```

---

# Critérios de Reprovação

✗ StyleSheet sem justificativa

✗ Inline Styles

✗ Cores hardcoded

✗ Espaçamentos arbitrários

✗ Ausência de Dark Mode

✗ Classes duplicadas

✗ Violação do Design System
