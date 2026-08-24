# Documentacao geral do e-Cidade

Este diretorio e a area principal para documentacao geral e tecnica do
e-Cidade-SD. O conteudo aqui deve ser escrito de forma aproveitavel pelo fork
principal do e-Cidade quando nao depender de processos internos da Sertao
Digital.

## Regra de localizacao

- `docs/` guarda documentacao geral, tecnica e operacional do e-Cidade-SD que
  pode ser compartilhada com o fork principal.
- `docs/sd/` guarda documentacao especifica da Sertao Digital, como handoffs,
  prompts internos e regras do processo SDKA. Esta pasta nao deve ser enviada ao
  fork principal sem revisao explicita.
- `docs/skills/` guarda Skills usadas no nosso trabalho sobre o e-Cidade-SD.
  Por serem operacionais do nosso processo, tambem nao devem ser enviadas ao
  fork principal sem revisao explicita.
- `ecidade/` guarda o sistema legado executavel.
- `ecidade/manuais/` deve permanecer dentro de `ecidade/` enquanto nao houver
  auditoria conclusiva de links, rotas, banco e deploy. Essa pasta possui
  arquivos servidos pelo legado e pode ser dependencia de runtime.

## Documentos iniciais

- `legacy-inventory.md`: inventario inicial da estrutura legada, manuais,
  ajuda do sistema e fontes de mapa de tabelas.
- `documentation-workflow.md`: fluxo para documentar cada area analisada.

## Como evoluir

Ao analisar uma parte do e-Cidade-SD, registre no mesmo ciclo:

1. contexto e escopo analisado;
2. entradas do codigo, telas, rotas, scripts e jobs;
3. tabelas e relacoes usadas;
4. fluxo operacional;
5. riscos, configuracoes e dependencias;
6. verificacoes feitas;
7. pendencias de documentacao, validacao e mapa de dados.

Documentacao incompleta e aceitavel quando deixa claro o escopo analisado, as
evidencias e as pendencias. O objetivo e reduzir risco aos poucos, sem prometer
um mapa completo antes de existir evidencia suficiente.
