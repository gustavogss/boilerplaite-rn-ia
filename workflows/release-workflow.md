# Release Workflow

## Objetivo

Garantir que toda versão seja entregue de forma previsível, rastreável, segura e validada.

Nenhuma versão pode ser publicada sem seguir este workflow.

---

# Fluxo Obrigatório

```text id="x01jmu"
Feature Complete
↓
Code Freeze
↓
QA Validation
↓
Security Validation
↓
Versionamento
↓
Release Notes
↓
Build Approval
↓
Release Candidate
↓
Produção
```

---

# Critérios para Iniciar Release

Obrigatório:

✓ Todas as features concluídas

✓ Todos os bugs críticos corrigidos

✓ Todos os PRs aprovados

✓ Testes passando

✓ Cobertura mínima atingida

---

# Code Freeze

Durante o período de release:

Proibido:

```text id="4pgwyu"
Novas funcionalidades
Grandes refatorações
Mudanças arquiteturais
```

Permitido:

```text id="7lksqx"
Correções críticas
Hotfixes
```

---

# Quality Gate

Executar:

✓ Unit Tests

✓ Integration Tests

✓ E2E Tests

✓ Accessibility Tests

✓ Performance Tests

✓ Security Tests

---

# Cobertura Mínima

```text id="hkgu5o"
80%
```

---

# Security Gate

Validar:

✓ Secrets

✓ Dependências

✓ Autorização

✓ Autenticação

✓ Variáveis de ambiente

✓ OWASP Mobile

---

# Versionamento

Utilizar:

```text id="syq08e"
Semantic Versioning
```

Formato:

```text id="vzwc5t"
MAJOR.MINOR.PATCH
```

Exemplos:

```text id="rgr5vk"
1.0.0
1.1.0
1.1.1
2.0.0
```

---

# Regras

## PATCH

```text id="6f48hk"
Correção de bug
```

Exemplo:

```text id="w2vgzv"
1.0.0 → 1.0.1
```

---

## MINOR

```text id="o7b6yv"
Nova funcionalidade
```

Exemplo:

```text id="r3g89y"
1.0.0 → 1.1.0
```

---

## MAJOR

```text id="uzjltq"
Breaking Changes
```

Exemplo:

```text id="jz1z8i"
1.0.0 → 2.0.0
```

---

# Release Notes

Obrigatório gerar:

```text id="gq3t5t"
Novidades
Correções
Melhorias
Breaking Changes
```

---

# Release Candidate

Criar:

```text id="wdgqzt"
RC
```

Exemplo:

```text id="4w7tdh"
1.4.0-rc.1
```

---

# Aprovação

Obrigatória:

✓ Tech Lead

✓ QA Agent

✓ Security Agent

✓ Reviewer Agent

---

# Critérios de Aprovação

✓ Todos os testes aprovados

✓ Nenhum bug crítico

✓ Nenhuma vulnerabilidade crítica

✓ Release Notes geradas

✓ Versão atualizada

---

# Critérios de Reprovação

✗ Testes falhando

✗ Cobertura insuficiente

✗ Vulnerabilidades críticas

✗ Falta de documentação

✗ Falta de aprovação

---

# Regra Suprema

Nenhuma release pode ser aprovada apenas porque "funciona na minha máquina".
