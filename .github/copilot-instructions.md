# e-Cidade-SD repository instructions

This repository contains the e-Cidade-SD module, based on the legacy e-Cidade
codebase.

## Documentation boundaries

- Use `docs/` for general e-Cidade technical and operational documentation that
  can be proposed to the main fork.
- Use `docs/sd/` for Sertao Digital internal process material, including Drive
  and SD-Knowledge handoffs.
- Use `docs/skills/` for local Skills used in our e-Cidade-SD work.
- Do not include `docs/sd/` or `docs/skills/` in upstream/main-fork
  contributions without explicit review.
- Keep `ecidade/manuais/` in the runtime tree until links, routes, database
  references and web serving behavior are fully audited.

## Development guidance

- Read the relevant legacy entrypoint before changing behavior.
- Map includes, RPC files, JavaScript, generated forms, `db_*` classes, models,
  repositories, SQL, `dd/tabelas` and migrations for the area being changed.
- Prefer narrow changes and document discovered operational or schema behavior
  as part of the same work.
- Never commit secrets, real credentials or unnecessary personal data.

## Windows checkout note

The legacy tree contains files whose paths differ only by letter case. On a
case-insensitive Windows checkout, Git may report modified files after reset.
Do not hide that state with index flags unless the limitation is explicitly
accepted for the local environment.
