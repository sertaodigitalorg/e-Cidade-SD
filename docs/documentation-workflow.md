# Fluxo de documentacao incremental do e-Cidade

Este fluxo deve ser usado sempre que uma parte do e-Cidade-SD for analisada,
corrigida, ativada ou migrada.

## Principios

- Documentar junto com a analise, nao apenas depois da implementacao.
- Separar evidencia observada de inferencia.
- Manter documentacao operacional e tecnica no repositorio quando ela explicar
  comportamento, instalacao, operacao ou arquitetura do e-Cidade-SD.
- Nao mover arquivos legados de runtime sem auditoria de impacto.

## Template por area analisada

Crie um arquivo em `docs/areas/<area-ou-modulo>.md` com:

```markdown
# <Area ou modulo>

Data da analise: AAAA-MM-DD
Escopo: <arquivos, telas, tabelas ou fluxo analisado>

## Resumo

<O que esta area faz e qual problema foi analisado.>

## Entradas do sistema

- Telas:
- Rotas/scripts:
- Jobs/comandos:
- APIs:

## Fluxo operacional

1. <passo observado>
2. <passo observado>
3. <passo observado>

## Mapa tecnico

- Arquivos principais:
- Classes/services:
- Formularios/funcoes:
- Dependencias externas:

## Tabelas

| Tabela | Uso | Evidencia |
| --- | --- | --- |
|  |  |  |

## Regras e riscos

- <regra de negocio ou risco tecnico>

## Verificacao

- <comando, tela, teste, consulta ou limitacao>

## Pendencias

- [ ] Codigo:
- [ ] Teste:
- [ ] Documentacao:
- [ ] Validacao funcional:
```

## Roteiro de analise de uma tela legada

1. Identificar o arquivo de entrada `.php`.
2. Procurar includes/requires, `modification(...)`, RPCs e scripts JS chamados.
3. Identificar classes `cl_*`, models, repositories e formularios `db_frm*`.
4. Mapear tabelas via consultas SQL, classes `db_*_classe.php` e XMLs em
   `dd/tabelas`.
5. Procurar menus e permissoes em `db_itensmenu`, `db_menu`, `db_permissao` e
   migrations relacionadas.
6. Registrar fluxo operacional e pontos de configuracao.
7. Registrar verificacao executada e pendencias.

## Roteiro de analise de manuais/ajuda

1. Verificar se a tela usa `db_itensmenu.help`.
2. Verificar se existe Help remoto por `DBHelpSistema` ou `DBHelpInline`.
3. Procurar links diretos para `manuais/`.
4. Procurar chamadas para `ecidade/manuais/index.php`.
5. Verificar se o servidor web serve arquivos estaticos de `manuais/`.
6. Registrar se o conteudo e runtime, manual de usuario, anexo historico ou
   candidato a migracao para `docs/`.

## Roteiro de mapa de tabelas

1. Comecar por uma area funcional, nao pelo sistema inteiro.
2. Listar XMLs correspondentes em `dd/tabelas`.
3. Relacionar classes `classes/db_*_classe.php`.
4. Procurar migrations que criam, alteram ou populam menu/tabela.
5. Mapear consultas SQL diretas no fluxo analisado.
6. Registrar confianca: `observado`, `inferido` ou `pendente de banco`.
