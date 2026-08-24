---
name: e-cidade-sd
description: Documentar, analisar e evoluir o modulo e-Cidade-SD respeitando a separacao entre legado executavel, documentacao geral e governanca interna Sertao Digital.
metadata:
  short-description: Trabalhar no e-Cidade-SD
---

# e-Cidade-SD

Use esta skill quando a tarefa envolver analise, documentacao, ativacao,
correcao ou evolucao do modulo e-Cidade-SD.

## Contexto essencial

- O sistema legado executavel fica em `ecidade/`.
- A documentacao geral do e-Cidade fica em `docs/`.
- Conteudo interno Sertao Digital fica em `docs/sd/` e Skills locais ficam em
  `docs/skills/`; essas pastas nao devem ser enviadas ao fork principal sem
  revisao explicita.
- `ecidade/manuais/` faz parte do legado executavel ate que uma auditoria de
  links, rotas, banco e deploy prove que pode ser movido.
- O e-Cidade possui arquivos com nomes que diferem apenas por maiusculas e
  minusculas; em Windows sem case sensitivity isso pode deixar o checkout sujo.

## Ao analisar uma area

1. Comece pelo arquivo de entrada, rota, job ou comando citado.
2. Mapeie includes, RPCs, JS, forms, classes `db_*`, models e repositories.
3. Relacione tabelas por consultas SQL, `dd/tabelas`, classes geradas e
   migrations.
4. Separe evidencia observada de inferencia.
5. Atualize a documentacao geral em `docs/` quando o achado for reutilizavel
   pelo e-Cidade.
6. Atualize ou crie handoff em `docs/sd/` quando o achado for interno da Sertao
   Digital, Drive ou SD-Knowledge.
7. Atualize `docs/skills/` quando a recorrencia justificar ajuste de Skill.

## Ao mexer em manuais ou ajuda

- Verifique `db_itensmenu.help`, `DBHelpSistema`, `DBHelpInline`, plugins e
  links diretos para `manuais/`.
- Nao mova `ecidade/manuais/` sem ADR e plano de compatibilidade.
- Registre o resultado em `docs/legacy-inventory.md` ou em um documento de area.

## Ao preparar contribuicao ao fork principal

- Inclua apenas documentacao e codigo gerais.
- Exclua `docs/sd/` e `docs/skills/` de PRs para o fork principal, salvo
  autorizacao explicita.
- Evite referencias a processos internos, Drive, SD-Knowledge ou governanca SDKA
  em documentos destinados ao fork principal.
