# Inventario inicial do legado e-Cidade-SD

Data da analise inicial: 2026-08-24.

## Estado do modulo

- Repositorio local: `modules/e-Cidade-SD`.
- Codigo executavel principal: `modules/e-Cidade-SD/ecidade`.
- Documentacao viva nova: `modules/e-Cidade-SD/docs`.
- O modulo foi alinhado ao `origin/main`, que tambem foi alinhado ao
  `upstream/master` no commit `e640eb485bf9a29f1fcda9c289c4ab23cffefe1d`.
- O checkout em Windows apresenta colisoes de caixa alta/baixa em alguns
  arquivos legados; isso afeta o status Git mesmo apos reset para `origin/main`.

## Estrutura observada

Diretorios relevantes dentro de `ecidade/`:

- `app/`, `src/`, `model/`, `classes/`, `funcoes/`, `forms/`: codigo PHP legado
  e camadas mais novas.
- `database/migrations/`: migrations PHP. Contagem inicial: 453 arquivos.
- `dd/tabelas/`: dicionario de dados em XML. Contagem inicial: 290 arquivos.
- `manuais/`: acervo legado de manuais e imagens.
- `assets/`, `scripts/`, `vue/`: assets e frontend legado/mais novo.
- `arquivos/esocial/tabelas/`: tabelas JSON de dominio, inclusive arquivos
  grandes que devem ser excluidos de buscas amplas.

## `ecidade/manuais`

Contagem inicial de arquivos em `ecidade/manuais`:

| Extensao | Quantidade |
| --- | ---: |
| `.png` | 5901 |
| `.jpg` | 179 |
| `.gif` | 141 |
| `.php` | 47 |
| `.html` | 32 |
| `.pdf` | 31 |
| `.zip` | 1 |
| `.odt` | 1 |
| `.odp` | 1 |

Diretorios de primeiro nivel observados incluem `agua`, `arrecadacao`,
`cadastro`, `compras`, `configuracao`, `contabilidade`, `contratos`,
`divida_ativa`, `educacao`, `empenho`, `issqn`, `itbi`, `licitacoes`,
`patrimonio`, `pessoal`, `rh`, `saude`, `tutoriais` e outros.

Arquivos soltos na raiz:

- `apresentapadroes.odp`
- `apresentapadroes.pdf`
- `index.php`

O arquivo `ecidade/manuais/index.php` monta dinamicamente um caminho de imagem
com `manuais/$modulo/$nome_imagem` e renderiza a imagem no navegador. Isso e
evidencia de uso potencial pelo sistema legado, nao apenas documentacao externa.

Recomendacao atual: nao mover `ecidade/manuais` para `docs/` nesta fase.
Primeiro e necessario mapear referencias por codigo, banco, help remoto,
servidor web e instaladores. Se a migracao for desejada depois, deve haver ADR,
plano de redirect/compatibilidade e teste de telas que abrem ajuda/manual.

## Ajuda do sistema

Evidencias iniciais:

- `ecidade/area.php` consulta `db_itensmenu.help` junto com `db_menu`,
  `db_modulos`, permissoes e areas.
- `model/configuracao/DbItensMenu.model.php` e
  `model/configuracao/MenuSistema.model.php` tratam o campo `help` do item de
  menu.
- `model/configuracao/DBCentralAjuda.model.php`,
  `DBHelpSistema.model.php` e `DBHelpInline.model.php` consomem uma API de
  central de ajuda configurada em `app.api.centraldeajuda`.
- `model/configuracao/PluginService.service.php` possui rotinas para instalar
  Help de plugins e vincular help a menu.

Conclusao inicial: a ajuda operacional do sistema nao depende apenas da pasta
`manuais/`. Existe uma camada de menu, campo `help`, API central de ajuda e
rotinas de plugin. O mapeamento completo depende de banco e configuracao.

## Fontes para mapa de tabelas

Fontes iniciais identificadas:

- `ecidade/dd/tabelas/*.dd.xml`: dicionario de dados por dominio/tabela.
- `ecidade/classes/db_*_classe.php`: DAOs legados gerados por tabela.
- `ecidade/forms/db_frm*.php`: formularios gerados/legados.
- `ecidade/funcoes/db_func_*.php`: funcoes de pesquisa e apoio por entidade.
- `ecidade/database/migrations/*.php`: evolucao de schema e menus.
- Consultas SQL embutidas em telas `.php`, services e repositories.

O mapa de tabelas deve ser incremental por area funcional. Uma tentativa de mapa
global sem recorte tende a misturar dominios e gerar baixa confiabilidade.

## Pendencias

- Mapear chamadas exatas para `ecidade/manuais/index.php` e URLs diretas para
  arquivos em `manuais/`.
- Verificar configuracao do servidor web/container para servir `manuais/`.
- Consultar base instalada para valores reais de `db_itensmenu.help`.
- Criar um primeiro mapa de tabelas por area escolhida, usando `dd/tabelas`,
  classes `db_*`, migrations e consultas.
- Definir criterio de quando uma descoberta fica em `docs/`, quando vira prompt
  para Drive e quando vira PR separado em SD-Knowledge.
