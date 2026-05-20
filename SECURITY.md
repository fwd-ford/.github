# Política de Segurança

Este documento descreve o tratamento de segurança e privacidade na org [fwd-ford](https://github.com/fwd-ford).

## Versões suportadas

Sprint 1 está em desenvolvimento ativo. A versão `main` é a versão suportada.

## Como reportar uma vulnerabilidade

**Não abra issue pública**. Em vez disso:

1. Envie um e-mail privado pra [@jota0802](https://github.com/jota0802) (responsável pela trust layer)
2. Inclua:
   - Descrição da vulnerabilidade
   - Passos de reprodução
   - Impacto potencial
   - Sugestão de mitigação (se tiver)

Você receberá resposta em até **48h**.

## Princípios de segurança ForwardService

A organização segue o **Trust Layer** (pilar 4 do produto):

### Validação e entrada
- Sanitização de entrada contra SQLi, XSS, command injection
- Validators com regex para parâmetros (VIN, dealer code, etc.)
- Limite de tamanho de payload

### Autenticação e autorização
- JWT HS256 + JWKS (validação dual)
- Roles: `analyst`, `admin`, `user`
- RBAC aplicado por filtro Spring Security

### Proteção em trânsito
- HTTPS/TLS 1.2+ obrigatório em produção
- Rate limiting por IP + sub (Bucket4j)
- CORS com whitelist explícita

### Proteção em repouso
- pgcrypto para colunas sensíveis (`phone`, `email`, `document`, mensagens)
- VIN_Hash SHA1 pseudonimizado (compliance LGPD)
- Política de retenção: ver `forward-infra/RETENTION_POLICY.md`

### Auditoria
- `audit_log` table para todas ações críticas
- Logs estruturados em JSON (Logback)
- Correlation ID por request

## Dependências

- [Dependabot](https://docs.github.com/code-security/dependabot) ativo em todos os repos
- Atualizações semanais de dependências
- Escaneamento Trivy + Gitleaks via workflows reutilizáveis

## Compliance LGPD

- Pseudonimização: VIN_Hash (SHA1 robusto, 5M tentativas de reversão = 0 matches)
- Direito ao esquecimento: soft-delete via `deleted_at`
- Anonimização para ML/dashboards: k-anonimização (k≥10) por agregação
