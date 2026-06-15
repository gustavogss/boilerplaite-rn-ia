# Incident Workflow

## Objetivo

Responder rapidamente a incidentes críticos em produção minimizando impacto aos usuários.

Este workflow possui prioridade máxima.

---

# Definição

Incidente é qualquer evento que:

- Afeta usuários reais
- Afeta produção
- Afeta receita
- Afeta segurança
- Afeta disponibilidade

---

# Exemplos

```text
Aplicativo não abre

Falha de login

Pagamento indisponível

Perda de dados

API fora do ar

Falha de autenticação

Vazamento de dados

Falha crítica de segurança
```

---

# Fluxo Obrigatório

```text
Detecção
↓
Classificação
↓
Mitigação
↓
Diagnóstico
↓
Correção
↓
Validação
↓
Deploy Emergencial
↓
Monitoramento
↓
Post Mortem
```

---

# Severidade

## SEV-1

Crítico

Exemplos:

```text
Pagamento indisponível
Vazamento de dados
Aplicação fora do ar
```

Resposta:

```text
Imediata
```

---

## SEV-2

Alta

Exemplos:

```text
Login indisponível
API principal instável
```

Resposta:

```text
Até 1 hora
```

---

## SEV-3

Média

Exemplos:

```text
Funcionalidade secundária
```

Resposta:

```text
Até 24 horas
```

---

## SEV-4

Baixa

Exemplos:

```text
Problemas visuais
Pequenos defeitos
```

Resposta:

```text
Próxima sprint
```

---

# Fase 1 - Mitigação

Prioridade:

Restaurar serviço.

Opções:

```text
Rollback
Feature Flag
Hotfix
Desativação temporária
```

---

# Regra

Primeiro estabilizar.

Depois corrigir.

---

# Fase 2 - Diagnóstico

Coletar:

- Logs
- Métricas
- Traces
- Evidências

Identificar:

```text
Causa raiz
Impacto
Escopo
```

---

# Fase 3 - Correção

Aplicar:

✓ Menor alteração possível

✓ Menor risco possível

✓ Menor tempo possível

---

# Fase 4 - Validação

Executar:

✓ Smoke Test

✓ Fluxo Principal

✓ Testes Automatizados

---

# Fase 5 - Deploy

Preferência:

```text
Hotfix Branch
```

Fluxo:

```text
main
↓
hotfix/*
↓
produção
```

---

# Fase 6 - Monitoramento

Monitorar:

- Erros
- Crash Rate
- Performance
- Logs
- Métricas

Mínimo:

```text
24 horas
```

---

# Post Mortem

Obrigatório para:

SEV-1

SEV-2

---

# Documento Post Mortem

Registrar:

## Resumo

## Impacto

## Timeline

## Root Cause

## Mitigação

## Correção

## Lições Aprendidas

## Ações Preventivas

---

# Responsabilidades

Tech Lead

- Coordenar incidente

Security Agent

- Avaliar riscos

DevSecOps Agent

- Coordenar deploy

QA Agent

- Validar correção

Reviewer Agent

- Revisar hotfix

Documentation Agent

- Criar Post Mortem

---

# Critérios de Encerramento

✓ Serviço restaurado

✓ Causa raiz identificada

✓ Correção implantada

✓ Monitoramento concluído

✓ Post Mortem criado

✓ Ações preventivas registradas

---

# Regra Suprema

Em incidentes críticos:

Estabilidade > Elegância

Primeiro restaurar o serviço.

Depois melhorar o código.
