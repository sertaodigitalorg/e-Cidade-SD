# AGENTS.md - e-Cidade-SD

Este repositorio contem o modulo e-Cidade-SD, baseado no legado e-Cidade.

## Regras de trabalho

1. Analise o codigo antes de alterar comportamento.
2. Trate `ecidade/` como sistema executavel legado.
3. Trate `docs/` como documentacao geral que pode ser proposta ao fork
   principal.
4. Trate `docs/sd/` como documentacao interna Sertao Digital e `docs/skills/`
   como Skills locais; nao envie essas pastas ao fork principal sem autorizacao
   explicita.
5. Nao mova `ecidade/manuais/` para `docs/` sem auditoria de chamadas, rotas,
   banco, servidor web e ADR.
6. Ao documentar uma area, registre evidencias, tabelas, fluxo operacional,
   riscos e pendencias.
7. Evite secrets, dados pessoais desnecessarios e credenciais reais.

## Observacao sobre Windows

O legado possui arquivos com nomes que diferem apenas por maiusculas e
minusculas. Em checkout Windows sem case sensitivity, o Git pode marcar arquivos
como modificados mesmo apos reset para HEAD. Nao mascare isso com
`assume-unchanged` sem registrar a limitacao.
