<div align="center">

# ForwardService

**Plataforma de retenção pós-venda Ford**

`Challenge Ford × FIAP 2026 • Desafio 02 — VIN Share`

[![Sprint 1](https://img.shields.io/badge/Sprint%201-24%2F05%2F2026-red?style=flat-square)](https://github.com/orgs/fwd-ford/projects/1)
[![Stack](https://img.shields.io/badge/stack-Java%2017%20%E2%80%A2%20Python%20%E2%80%A2%20React%20Native-blue?style=flat-square)]()

</div>

---

## Equipe

| Nome | RM | Função | GitHub |
|---|---|---|---|
| João Victor Franco (Jota) | 556790 | Líder, coringa, Mobile | [@jota0802](https://github.com/jota0802) |
| Lucca Borges | 554608 | ML / Data | [@lucksza](https://github.com/lucksza) |
| Ruan Melo | 557599 | Backend / SOA | [@DevRuanVieira](https://github.com/DevRuanVieira) |
| Rodrigo Jimenez (Roji) | 558148 | QA / Produto | — |

## Visão geral

ForwardService cruza eventos do dataset oficial Ford VIN Share com modelos de churn comportamental, escala via mobile e dashboard, e automatiza reengajamento via n8n / WhatsApp.

**4 pilares:**
1. 🧠 **Intelligence Hub** — segmentação K-means + classificação de churn
2. 📲 **Customer Channel** — app cliente com histórico do VIN e agendamento
3. 🎯 **Dealer Cockpit** — leads priorizados para a concessionária
4. 🔒 **Trust Layer** — LGPD-first, criptografia em repouso, audit log

## Repositórios

| Repositório | Stack | Responsável |
|---|---|---|
| [forward-api-java](https://github.com/fwd-ford/forward-api-java) | Spring Boot 3 + Java 17 (REST + SOAP) | Ruan |
| [forward-ml](https://github.com/fwd-ford/forward-ml) | Python + scikit-learn + XGBoost | Lucca |
| [forward-mobile](https://github.com/fwd-ford/forward-mobile) | React Native + Expo + TypeScript | Jota |
| [forward-infra](https://github.com/fwd-ford/forward-infra) | Supabase + Postgres + Docker | Jota |
| [forward-docs](https://github.com/fwd-ford/forward-docs) | Documentação técnica + acadêmica + entregáveis de sprint | Todos |
| [forward-web](https://github.com/fwd-ford/forward-web) | SvelteKit (reservado p/ Sprint 3+) | — |

## Sprint atual

**Sprint 1** — deadline `24/05/2026` — [📋 board kanban](https://github.com/orgs/fwd-ford/projects/1)

Disciplinas avaliativas: SOA · Mobile · Testing/QA · Cybersecurity · IA/ML

## Disciplinas Ford × FIAP 2026

| # | Disciplina | Professor | Repo principal |
|---|---|---|---|
| 1 | Arquitetura SOA & Web Services | Salatiel Marinho | forward-api-java |
| 2 | Mobile Development & IoT | Hercules Lima Ramos | forward-mobile |
| 3 | Testing, Compliance & QA | Elias Bernardo | forward-docs |
| 4 | Cybersecurity | Vitor Miguel Lasse Silva | (transversal) |
| 5 | IA & Machine Learning | Carlos Fontoura | forward-ml |

## CI compartilhado

Este repositório (`.github`) hospeda os **workflows reutilizáveis** chamados pelos demais repos da organização.

- `java-quality.yml` — Spotless + Checkstyle + SpotBugs + JUnit
- `java-security.yml` — Trivy + OWASP Dependency Check + CodeQL SAST
- `secrets-scan.yml` — Gitleaks (escaneamento de credenciais)
- `docs-quality.yml` — markdownlint + verificação de links quebrados

Como usar a partir de um repo da org:

```yaml
jobs:
  quality:
    uses: fwd-ford/.github/.github/workflows/java-quality.yml@main
```

## Contribuindo

Issues, perguntas e propostas vão para o [board do Project](https://github.com/orgs/fwd-ford/projects/1) ou diretamente no repositório relevante.

Padrões da org:
- [CONTRIBUTING](https://github.com/fwd-ford/.github/blob/main/CONTRIBUTING.md) — fluxo de PRs, conventional commits, code review
- [SECURITY](https://github.com/fwd-ford/.github/blob/main/SECURITY.md) — relato de vulnerabilidades e LGPD
- Templates de issue e PR aplicam-se a todos os repos
