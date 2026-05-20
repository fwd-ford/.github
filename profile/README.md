# ForwardService — Ford Challenge 2026

Organização da equipe **Forward Service** no Ford Mobility Challenge 2026 (Desafio 02: VIN Share).

## Repositórios

- [forward-api-java](https://github.com/fwd-ford/forward-api-java) — Backend oficial (Spring Boot 3, Java 17).
- [forward-web](https://github.com/fwd-ford/forward-web) — Frontend SvelteKit.
- [forward-ml](https://github.com/fwd-ford/forward-ml) — Pipeline de ML (segmentação e classificação).
- [forward-mobile](https://github.com/fwd-ford/forward-mobile) — Aplicativo mobile.
- [forward-infra](https://github.com/fwd-ford/forward-infra) — IaC e configurações.
- [forward-docs](https://github.com/fwd-ford/forward-docs) — Documentação acadêmica e técnica.
- [forward-sprints](https://github.com/fwd-ford/forward-sprints) — Entregas por sprint.

## CI compartilhado

Este repositório (`.github`) hospeda os **workflows reutilizáveis** chamados pelos demais repos da organização.

- `java-quality.yml` — Spotless + Checkstyle + SpotBugs + JUnit.
- `java-security.yml` — Trivy + OWASP Dependency Check + CodeQL SAST.
- `secrets-scan.yml` — Gitleaks (escaneamento de credenciais).
- `docs-quality.yml` — markdownlint + verificação de links quebrados.

Como usar a partir de um repo da org:

```yaml
jobs:
  quality:
    uses: fwd-ford/.github/.github/workflows/java-quality.yml@main
```
