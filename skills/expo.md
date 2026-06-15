# Expo Standards

## Objetivo

Garantir que todos os projetos sejam desenvolvidos seguindo a filosofia Expo First.

A IA deve sempre priorizar soluções compatíveis com Expo antes de considerar bibliotecas nativas.

---

# Stack Base Obrigatória

Todo projeto deve utilizar:

- Expo
- React Native
- TypeScript
- NativeWind
- Shadcn UI
- Zod

---

# Filosofia Expo First

Antes de instalar qualquer biblioteca, verificar se existe solução oficial do Expo.

Prioridade:

```text
Expo SDK
↓
React Native Oficial
↓
Bibliotecas compatíveis com Expo
↓
Bibliotecas nativas
```

---

# Criação do Projeto

Obrigatório:

```bash
npx create-expo-app@latest
```

ou

```bash
npx create-expo-app@latest --template
```

---

# Router

Preferência:

```text
Expo Router
```

Estrutura:

```text
src/
└── app/
    ├── screens/
    ├── navigation/
    └── routes/
```

Não criar sistemas de navegação customizados sem justificativa.

---

# TypeScript

Obrigatório:

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

# Alias

Sempre utilizar:

```ts
import { Button } from "@/components/ui/Button";
```

Nunca:

```ts
import { Button } from "../../../components/ui/Button";
```

---

# Assets

Todos os assets devem ficar em:

```text
src/assets/
```

Estrutura:

```text
src/assets/
├── images/
├── icons/
├── fonts/
└── animations/
```

---

# Fontes

Utilizar:

```text
expo-font
```

Nunca utilizar carregamento manual.

---

# Splash Screen

Utilizar:

```text
expo-splash-screen
```

A Splash Screen deve aguardar:

- fontes
- tema
- autenticação inicial

---

# Armazenamento

## Dados Sensíveis

Utilizar:

```text
expo-secure-store
```

Exemplos:

- JWT
- Refresh Token
- Chaves de acesso

---

## Dados Não Sensíveis

Utilizar:

```text
AsyncStorage
```

Exemplos:

- Preferências
- Tema
- Configurações

---

# Permissões

Utilizar APIs Expo.

Exemplos:

```text
expo-camera
expo-image-picker
expo-location
expo-notifications
expo-media-library
```

Evitar bibliotecas externas quando houver alternativa oficial.

---

# Imagens

Utilizar:

```tsx
Image;
```

ou

```tsx
expo - image;
```

Preferência:

```text
expo-image
```

---

# Ícones

Utilizar:

```text
@expo/vector-icons
```

Proibido instalar bibliotecas adicionais de ícones sem necessidade.

---

# Autenticação

Preferência:

```text
Supabase Auth
Firebase Auth
Clerk
```

Nunca armazenar tokens em texto puro.

---

# Deep Linking

Utilizar:

```text
expo-linking
```

Configurar:

- Universal Links
- Deep Links
- Rotas protegidas

---

# Notificações

Utilizar:

```text
expo-notifications
```

Não implementar soluções próprias.

---

# Atualizações OTA

Obrigatório utilizar:

```text
expo-updates
```

Sempre que possível.

---

# Variáveis de Ambiente

Utilizar:

```env
EXPO_PUBLIC_API_URL=
EXPO_PUBLIC_SUPABASE_URL=
EXPO_PUBLIC_SUPABASE_ANON_KEY=
```

Acessar:

```ts
process.env.EXPO_PUBLIC_API_URL;
```

---

# Build

Utilizar:

```text
EAS Build
```

Nunca depender de builds locais para produção.

---

# Deploy

Obrigatório:

```text
EAS Build
EAS Submit
```

Fluxo:

```text
Development
↓
Preview
↓
Production
```

---

# Dependências

Antes de instalar qualquer biblioteca:

Verificar:

```bash
npx expo install
```

Preferir:

```bash
npx expo install package-name
```

Evitar:

```bash
npm install package-name
```

quando a dependência possuir integração Expo.

---

# Compatibilidade

Toda dependência deve ser:

✓ Compatível com Expo

✓ Compatível com EAS Build

✓ Compatível com SDK atual

---

# Performance

Utilizar:

```tsx
FlashList;
```

quando houver listas extensas.

Evitar:

```tsx
ScrollView;
```

para grandes volumes de dados.

---

# Offline First

Sempre que possível:

- Cache local
- Retry automático
- Sincronização posterior

---

# Segurança

Obrigatório:

- Expo Secure Store
- Variáveis de ambiente
- HTTPS
- Sanitização de entradas
- Validação com Zod

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

---

# Critérios de Reprovação

Reprovar automaticamente quando:

✗ Biblioteca nativa possuir alternativa Expo

✗ Uso de API nativa sem necessidade

✗ Tokens armazenados em AsyncStorage

✗ Dependência incompatível com Expo

✗ Ausência de EAS Build

✗ Ausência de Expo Secure Store

✗ Uso excessivo de bibliotecas externas

✗ Imports relativos excessivos

✗ Violação da arquitetura padrão

✗ Código incompatível com Expo Go sem justificativa

---

# Regra Suprema

Todo agente deve assumir que o projeto é Expo First.

Antes de sugerir qualquer biblioteca:

1. Verificar se existe solução oficial Expo.
2. Verificar compatibilidade com Expo SDK atual.
3. Verificar compatibilidade com EAS Build.
4. Somente então considerar alternativas externas.
