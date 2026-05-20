# Contribuindo com ForwardService

Bem-vindo! Este documento define o fluxo padrão de contribuição em qualquer repositório da org [fwd-ford](https://github.com/fwd-ford).

## Quem pode contribuir

Membros do grupo Sprint 1 (Jota, Lucca, Ruan, Roji) têm acesso direto. Externos abrem issue antes de PR.

## Fluxo de trabalho

1. **Pegue (ou abra) uma issue** no [board do Project](https://github.com/orgs/fwd-ford/projects/1)
2. **Crie uma branch** a partir de `main`:
   ```
   git checkout -b feat/breve-descricao
   ```
3. **Commits** seguindo [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/):
   - `feat:` nova feature
   - `fix:` bug fix
   - `chore:` tarefa rotineira (deps, configs)
   - `docs:` só documentação
   - `refactor:` mudança de código sem mudar comportamento
   - `test:` adicionar/ajustar testes
4. **Abra a PR** preenchendo o template
5. **Code review** — Jota é o reviewer default (CODEOWNERS). Pelo menos 1 aprovação antes do merge.
6. **Merge** preferencialmente via "Squash and merge" pra histórico limpo

## Padrões de código

- **Idioma**: comentários de código em inglês, mensagens de UI/relatórios em pt-BR
- **Sem segredos hardcoded** — usar `.env.example` como referência
- **Sem mock que vire produção** — marcar mocks com `// MOCK:` ou pra remover

## Branches protegidas

`main` é protegida em todos os repos:
- Não pode commit direto (PR obrigatório)
- Pelo menos 1 aprovação
- CI verde antes do merge

## Issues e PRs

- **Antes de abrir**: confira se já existe issue/PR aberta sobre o tema
- **Templates**: use os templates de issue/PR
- **Labels**: aplique `sprint-1` e a label do time correspondente

## Dúvidas?

- Slack/WhatsApp do grupo
- Issue no repo relevante
