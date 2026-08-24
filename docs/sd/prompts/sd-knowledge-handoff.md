# Prompt de handoff para SD-Knowledge, Agents ou Skills

Use este modelo quando uma descoberta do e-Cidade-SD indicar regra tecnica
reutilizavel, padrao transversal, ajuste de governanca, criacao/alteracao de
Agent ou Skill, ou aprendizado que afete outros produtos Sertao Digital.

```text
Contexto:
Durante trabalho no modulo e-Cidade-SD, foi identificada uma regra ou pratica
tecnica que pode ser reutilizavel ou transversal.

Repositorio de origem:
- LegislaGD/e-Cidade-SD
- Caminho local:
- Branch/commit, se houver:

Descoberta:
<descrever objetivamente a regra, padrao, risco ou aprendizado>

Evidencias:
- <arquivo:linha>
- <documento/ADR relacionado>
- <comando ou verificacao>

Impacto transversal:
- Produtos afetados:
- Skills/Agents possivelmente afetados:
- Riscos de seguranca, privacidade ou compatibilidade:

Proposta:
<o que deve ser atualizado no SD-Knowledge, Agent ou Skill>

Separacao de PRs:
Abrir PR separado no SD-Knowledge, sem misturar historico ou arquivos do
e-Cidade-SD. Referenciar o PR do e-Cidade-SD quando existir.
```
