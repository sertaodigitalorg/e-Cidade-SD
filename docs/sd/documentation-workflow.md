# Fluxo interno de documentacao Sertao Digital

Este complemento cobre apenas a parte interna do processo. A documentacao geral
do e-Cidade fica em `docs/`; handoffs e integracoes com SD-Knowledge ou Drive
ficam em `docs/sd/`; Skills locais ficam em `docs/skills/`.

## Quando gerar handoff

- Drive: conhecimento funcional, institucional, juridico, administrativo,
  comercial ou operacional que precise virar fonte fora do repositorio.
- SD-Knowledge: regra tecnica reutilizavel, governanca transversal, padrao que
  afete outros produtos ou ajuste de Skill/Agent.
- Skill local: recorrencia de trabalho no e-Cidade-SD que mude a forma de
  analisar, documentar ou evoluir o modulo.

## Checklist interno

- [ ] A descoberta geral foi registrada fora de `docs/sd/`.
- [ ] O conteudo interno foi mantido em `docs/sd/`.
- [ ] Foi gerado prompt de handoff quando nao houve acesso direto ao destino.
- [ ] PRs de e-Cidade-SD e SD-Knowledge, quando existirem, ficaram separados.
- [ ] Referencias cruzadas usam numeros reais de PR/issue/commit.
