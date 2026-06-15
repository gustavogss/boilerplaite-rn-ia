# Deploy Workflow

## Objetivo

Garantir deploy seguro, reproduzível e auditável em todos os ambientes.

---

# Ambientes

Obrigatórios:

```text id="m2k9ea"
Development
Preview
Production
```

---

# Fluxo

```text id="ec0j0g"
Build
↓
Deploy Development
↓
Validação
↓
Deploy Preview
↓
Validação
↓
Deploy Production
↓
Monitoramento
```

---

# Expo

Obrigatório:

```text id="7d7h8s"
EAS Build
EAS Submit
EAS Update
```

---

# Build

Executar:

```bash id="w4t4w7"
eas build
```

---

# Atualizações OTA

Utilizar:

```bash id="ytwpk2"
eas update
```

Quando:

- Não houver mudança nativa
- Não houver mudança de SDK

---

# Build Nativa

Obrigatória quando:

- SDK alterado
- Dependência nativa alterada
- Permissões alteradas

---

# Checklist Pré Deploy

✓ Build aprovado

✓ Testes aprovados

✓ Variáveis configuradas

✓ Secrets configurados

✓ Versionamento atualizado

✓ Changelog atualizado

---

# Variáveis de Ambiente

Development:

```env id="s1mmtf"
EXPO_PUBLIC_API_URL=
```

Preview:

```env id="gjd8m2"
EXPO_PUBLIC_API_URL=
```

Production:

```env id="c4m7ka"
EXPO_PUBLIC_API_URL=
```

---

# Secrets

Nunca:

```ts id="q6sukg"
const apiKey = "123";
```

Sempre:

```text id="h4zjwr"
EAS Secrets
Environment Variables
```

---

# Monitoramento

Após deploy:

Monitorar:

✓ Crash Rate

✓ API Errors

✓ Login

✓ Performance

✓ Métricas de negócio

---

# Tempo de Observação

Mínimo:

```text id="d1gq3s"
24 horas
```

---

# Rollback

Condições:

```text id="ztkw4r"
Crash crítico
Falha de login
Falha de pagamento
Perda de dados
```

---

# Procedimento

```text id="h59db3"
Detectar
↓
Avaliar
↓
Rollback
↓
Monitorar
↓
Post Mortem
```

---

# Deploy em Produção

Necessita:

✓ Release aprovada

✓ QA aprovado

✓ Security aprovado

✓ DevSecOps aprovado

---

# Critérios de Aprovação

✓ Aplicação saudável

✓ Sem aumento de crashes

✓ Sem aumento de erros

✓ Fluxos críticos funcionando

---

# Critérios de Reprovação

✗ Build falhando

✗ Variáveis ausentes

✗ Vulnerabilidades críticas

✗ Falhas em produção

✗ Testes falhando

---

# Responsabilidades

DevSecOps Agent

- Pipeline
- Build
- Deploy

QA Agent

- Validação

Security Agent

- Segurança

Reviewer Agent

- Aprovação

Tech Lead

- Go/No-Go

---

# Regra Suprema

Nenhum deploy em produção pode ocorrer sem possibilidade de rollback.
