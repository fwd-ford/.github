# Contribuindo com ForwardService

Bem-vindo! Este documento define o fluxo padrao de contribuicao em qualquer repositorio da org [fwd-ford](https://github.com/fwd-ford).

## Quem pode contribuir

Membros do grupo Sprint 1 (Jota, Lucca, Ruan, Roji) tem acesso direto. Externos abrem issue antes de PR.

## Fluxo de trabalho

1. **Pegue (ou abra) uma issue** no [board do Project](https://github.com/orgs/fwd-ford/projects/1)
2. **Crie uma branch** a partir de `main`:

   ```bash
   git checkout -b feat/breve-descricao
   ```

3. **Commits** seguindo [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/):
   - `feat:` nova feature
   - `fix:` bug fix
   - `chore:` tarefa rotineira (deps, configs)
   - `docs:` so documentacao
   - `refactor:` mudanca de codigo sem mudar comportamento
   - `test:` adicionar/ajustar testes
4. **Abra a PR** preenchendo o template.
5. **Code review** opcional. Jota e o reviewer default (CODEOWNERS). Aprovacao nao e obrigatoria pra mergear, mas peca em mudancas nao triviais.
6. **Merge** preferencialmente via "Squash and merge" pra historico limpo.

## Padroes de codigo

- **Idioma**: codigo, identificadores e comentarios em ingles. Documentos, mensagens de UI e PR description em pt-BR.
- **Sem em dashes nem en dashes** em lugar nenhum.
- **Sem segredos hardcoded**: usar `.env.example` como referencia.
- **Sem mock que vire producao**: marcar mocks com `// MOCK:` ou remover antes de mergear.

## Branches protegidas (ruleset "Protect main")

`main` e protegida em todos os repos via repository ruleset:

- Nao da pra push direto: PR obrigatorio.
- Nao da pra force push.
- Nao da pra deletar.
- Aprovacao nao e exigida hoje (vale o bom senso de pedir review em PR grande ou risky).
- CI roda em PR; merge nao bloqueia se CI estiver vermelho, mas resolva antes.

Se precisar mudar uma regra, edite o ruleset em Settings - Rules - Rulesets.

## Onde olhar primeiro

- Setup local: `forward-repos/RUNNING_LOCALLY.md`.
- Status do Sprint 1: `forward-repos/forward-docs/project/FOLLOW_UP_2026-05-17.md`.
- Briefing oficial Ford: `Ford.pdf` no workspace raiz.

## Primeira PR de quem nunca abriu

```bash
git checkout main && git pull
git checkout -b feat/seu-assunto
# faz suas mudancas
git add .
git commit -m "feat: o que voce fez"
git push -u origin feat/seu-assunto
gh pr create   # ou abre no GitHub UI
```

Duvida pinga o Jota no grupo.
