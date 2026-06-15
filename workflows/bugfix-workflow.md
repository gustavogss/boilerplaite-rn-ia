# Bug Fix Workflow

## Objetivo

Garantir que correções sejam realizadas de forma controlada, segura, rastreável e sem introduzir regressões.

Nenhum bug deve ser corrigido sem investigação prévia.

---

# Fluxo Obrigatório

```text
Bug Report
↓
Reprodução
↓
Análise de Causa Raiz
↓
Plano de Correção
↓
Implementação
↓
Testes
↓
Code Review
↓
QA Validation
↓
Documentação
↓
Entrega
```

---

# Fase 1 - Recebimento do Bug

Registrar:

- Descrição
- Ambiente
- Plataforma
- Versão
- Severidade
- Evidências

Exemplo:

```text
Tela:
Login

Erro:
Aplicação fecha ao clicar em Entrar

Plataforma:
Android

Versão:
1.0.5

Severidade:
Alta
```

---

# Fase 2 - Reprodução

Objetivo:

Confirmar que o problema realmente existe.

Registrar:

- Passos para reproduzir
- Resultado esperado
- Resultado atual

Exemplo:

```text
1. Abrir app
2. Acessar Login
3. Informar credenciais
4. Clicar Entrar

Resultado esperado:
Usuário autenticado

Resultado atual:
Aplicação fecha inesperadamente
```

---

# Regra

Nunca corrigir um bug sem reproduzi-lo.

---

# Fase 3 - Análise de Causa Raiz

Identificar:

- Onde ocorre
- Por que ocorre
- Qual impacto

Classificar:

```text
UI
Navigation
State
Service
API
Database
Validation
Authentication
Authorization
Performance
Security
Configuration
```

---

# Root Cause Analysis

Perguntas obrigatórias:

```text
O que causou o bug?

Por que não foi detectado?

Existe outro local afetado?

Existe risco de regressão?
```

---

# Fase 4 - Plano de Correção

Definir:

- Arquivos impactados
- Componentes impactados
- Testes necessários
- Riscos

Exemplo:

```text
Arquivos:
authService.ts
LoginScreen.tsx

Impacto:
Autenticação

Risco:
Baixo
```

---

# Regra

Corrigir apenas o necessário.

Evitar refatorações durante correções simples.

---

# Fase 5 - Implementação

Antes de alterar código:

Consultar:

```text
rules/
├── coding-standards.md
├── security.md
├── testing.md
└── architecture.md
```

---

# Implementação

Obrigatório:

✓ Menor alteração possível

✓ Tipagem correta

✓ Sem any

✓ Sem quebra de arquitetura

✓ Sem duplicação

---

# Proibido

```text
Refatorar módulos inteiros
Reescrever funcionalidades
Adicionar dependências sem necessidade
```

---

# Fase 6 - Testes

Executar:

## Unit Tests

```text
Services
Hooks
Utils
Schemas
```

---

## Integration Tests

```text
Screen
Hook
Service
API
```

---

## Regressão

Validar:

```text
Fluxo original
Fluxo corrigido
Fluxos relacionados
```

---

# Regra

Toda correção deve possuir teste que reproduza o bug.

---

# Exemplo

Se:

```text
Login quebra ao enviar senha vazia
```

Criar teste:

```text
deve impedir login com senha vazia
```

---

# Fase 7 - Security Review

Verificar:

- Exposição de dados
- Validações
- Autenticação
- Autorização

Consultar:

```text
security.md
devsecops.md
```

---

# Fase 8 - Code Review

Checklist:

✓ Arquitetura respeitada

✓ Código limpo

✓ Testes atualizados

✓ Sem regressão

✓ Sem duplicação

✓ Sem vulnerabilidades

---

# Fase 9 - QA Validation

Executar:

```text
Teste Manual
Teste Automatizado
Teste de Regressão
```

---

# Fase 10 - Documentação

Registrar:

## Bug

Descrição original.

---

## Root Cause

Motivo identificado.

---

## Correção

O que foi alterado.

---

## Testes

O que foi validado.

---

# Classificação de Severidade

## Crítica

Impacta:

```text
Pagamento
Autenticação
Segurança
Dados do usuário
```

Prazo:

```text
Imediato
```

---

## Alta

Impacta:

```text
Fluxos principais
```

Prazo:

```text
24 horas
```

---

## Média

Impacta:

```text
Funcionalidade secundária
```

Prazo:

```text
Sprint atual
```

---

## Baixa

Impacta:

```text
UX
Visual
Pequenos ajustes
```

Prazo:

```text
Backlog
```

---

# Critérios de Aprovação

✓ Bug reproduzido

✓ Causa raiz identificada

✓ Correção implementada

✓ Testes criados

✓ Testes aprovados

✓ Regressão validada

✓ Review aprovado

✓ QA aprovado

✓ Documentação atualizada

---

# Critérios de Reprovação

✗ Bug não reproduzido

✗ Sem análise de causa raiz

✗ Correção sem testes

✗ Correção sem validação

✗ Introdução de regressões

✗ Quebra da arquitetura

✗ Uso de any

✗ Refatoração desnecessária

✗ Ausência de documentação

✗ Ausência de revisão

---

# Responsabilidades dos Agentes

Product Manager

- Registrar bug

Architect

- Avaliar impacto arquitetural

Tech Lead

- Planejar correção

Frontend Agent

- Corrigir problemas de UI

Backend Agent

- Corrigir APIs e regras de negócio

Security Agent

- Avaliar riscos de segurança

DevSecOps Agent

- Garantir conformidade

QA Agent

- Validar correção

Reviewer Agent

- Aprovar ou reprovar

Documentation Agent

- Atualizar documentação

---

# Regra Suprema

Nunca corrigir um sintoma.

Sempre corrigir a causa raiz do problema.

Se a causa raiz não for identificada, a correção não pode ser considerada concluída.
