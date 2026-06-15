# Boilerplate RN IA

**AI Development System para React Native** — Um conjunto estruturado de artefatos, regras, agentes e workflows para guiar IAs durante o ciclo de vida completo de desenvolvimento de apps React Native com Expo, TypeScript, NativeWind, Shadcn UI e Zod.

> 🧠 Projetado para manter a IA focada, consistente e alinhada com boas práticas — sem fugir do contexto.

---

## Stack

| Tecnologia | Propósito |
|-----------|-----------|
| [Expo](https://expo.dev) | Framework e build system |
| [React Native](https://reactnative.dev) | UI mobile cross-platform |
| [TypeScript](https://typescriptlang.org) | Tipagem estática (`strict: true`) |
| [NativeWind](https://nativewind.dev) | Estilização utility-first |
| [Shadcn UI](https://ui.shadcn.com) | Componentes reutilizáveis |
| [Zod](https://zod.dev) | Validação de esquemas |
| [React Hook Form](https://react-hook-form.com) | Gerenciamento de formulários |
| Jest + React Native Testing Library | Testes unitários e de componentes |
| Detox / Maestro | Testes E2E |

---

## Estrutura do Projeto

```
├── system.md                          → Fluxo mestre obrigatório
├── agents/                            → 11 papéis especializados de IA
├── rules/                             → 10 conjuntos de regras obrigatórias
├── skills/                            → 6 skills técnicas detalhadas
├── workflows/                         → 6 workflows operacionais
└── doc/core/                          → Documentos de design (PRD, SDD)
```

---

## Fluxo Obrigatório

```
Ideia → PRD → SDD → Tasks → Implementação → QA → Security → DevSecOps → Performance → Review → Documentação → Entrega
```

Nenhuma etapa pode ser pulada. Nenhum código antes de PRD, SDD e Feature Spec estarem completos.

---

## Sistema Principal

- [system.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/system.md) — Fluxo mestre do sistema

---

## Agentes

Agentes especializados que compõem o time de desenvolvimento orientado por IA:

- [agents/architect.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/architect.md)
- [agents/backend.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/backend.md)
- [agents/devsecops.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/devsecops.md)
- [agents/documentation.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/documentation.md)
- [agents/frontend.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/frontend.md)
- [agents/performance.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/performance.md)
- [agents/product-manager.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/product-manager.md)
- [agents/qa.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/qa.md)
- [agents/reviewer.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/reviewer.md)
- [agents/security.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/security.md)
- [agents/tech-lead.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/agents/tech-lead.md)

---

## Regras

Conjuntos obrigatórios que toda interação da IA deve seguir:

- [rules/architecture.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/architecture.md) — Estrutura de pastas e padrões de arquitetura
- [rules/coding-standards.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/coding-standards.md) — Padrões de código (SOLID, DRY, KISS, YAGNI)
- [rules/components.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/components.md) — Regras para criação de componentes
- [rules/security.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/security.md) — Práticas de segurança
- [rules/testing.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/testing.md) — Pirâmide de testes e cobertura mínima
- [rules/theme.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/theme.md) — Sistema de temas (Light/Dark/System)
- [rules/typescript.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/typescript.md) — Configuração e boas práticas TypeScript
- [rules/ui.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/ui.md) — Diretrizes de interface com NativeWind + Shadcn
- [rules/validation.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/validation.md) — Validação de entradas com Zod
- [rules/workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/rules/workflow.md) — Regras do fluxo de trabalho

---

## Skills

Guias técnicos aprofundados para cada tecnologia do stack:

- [skills/expo.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/skills/expo.md)
- [skills/nativewind.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/skills/nativewind.md)
- [skills/react-native.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/skills/react-native.md)
- [skills/shadcn.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/skills/shadcn.md)
- [skills/typescript.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/skills/typescript.md)
- [skills/zod.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/skills/zod.md)

---

## Workflows

Processos operacionais detalhados passo a passo:

- [workflows/feature-workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/workflows/feature-workflow.md)
- [workflows/bugfix-workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/workflows/bugfix-workflow.md)
- [workflows/refactor-workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/workflows/refactor-workflow.md)
- [workflows/incident-workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/workflows/incident-workflow.md)
- [workflows/release-workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/workflows/release-workflow.md)
- [workflows/deploy-workflow.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/workflows/deploy-workflow.md)

---

## Documentos de Design

- [doc/core/prd.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/doc/core/prd.md) — Product Requirements Document
- [doc/core/sdd.md](https://github.com/gustavogss/boilerplaite-rn-ia/blob/main/doc/core/sdd.md) — Software Design Document

---

## Licença

Este projeto é open source. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
