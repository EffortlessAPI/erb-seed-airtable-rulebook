# Airtable Rulebook Seed

A rulebook extracted from an Airtable base, plus everything that can be
derived from it. The extraction has already happened when this project
reaches you — `effortless-rulebook/effortless-rulebook.json` IS your base,
as a rulebook you own.

## What `effortless build` produces

| Folder | From | What it is |
|---|---|---|
| `postgres/` | rulebook-to-postgres | The schema, `vw_*` views, functions and seed data |
| `docs/` | rulebook-to-markdown | Documentation of every table, field and rule |
| `rulespeak/` | rulebook-to-rulespeak | Business-readable RuleSpeak statements |
| `explainer-dag/` | rulebook-to-explainer-dag | Interactive dependency graph of every derived value |
| `xlsx/` | rulebook-to-xlsx | An Excel workbook with the model and live formulas |
| `effortless-rulebook/docker/` | effortless-rulebook-editor | A Docker image: Postgres + the generated API + the browser rulebook editor |

## Pulling from the base again

The `airtable-to-rulebook` step is registered but **disabled**: a normal
`effortless build` never calls Airtable and needs no credentials. To make the
rulebook follow the base again:

```bash
effortless -setAccountAPIKey airtable=<your PAT>   # stored in ~/.ssotme, not the repo
effortless build -id                               # -id runs disabled steps too
```

## Getting started

```bash
effortless build
./effortless-rulebook/edit-rulebook.sh      # open the rulebook editor (needs Docker)
```

## Requirements

- the `effortless` CLI (`npm i -g @effortlessapi/cli`), signed in
- Docker, only for the rulebook editor
- an Airtable PAT, only to re-pull from the base
