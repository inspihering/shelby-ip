# Shelby IP Archive

**Repository classification:** Private, owner-designated source materials
**Purpose:** Preserve the original skill files and supporting documentation that informed Cadence Command Center and related speaker-business products.

## What belongs here

This repository contains the original `.skill` source files, their integrity manifest, and documentation describing their intended product relationship. The files in `skills/` are stored as source artifacts. Their text is not reformatted, rewritten, or mixed with application code.

## What does not belong here

Do not add member data, customer records, Airtable exports, payment data, application credentials, API keys, environment files, generated product data, or production configuration. Cadence implementation code belongs in the separate private [`cadence-command-center`](https://github.com/inspihering/cadence-command-center) repository.

## Repository layout

```text
skills/   Original source skill files, preserved exactly
/docs     Inventory, integrity records, and repository governance
```

## Source handling rules

1. Treat each file in `skills/` as an original source artifact.
2. Make edits through a documented pull request or commit that explains the substantive framework change.
3. Update `docs/IP-INVENTORY.md` whenever a source file changes or a new one is added.
4. Do not copy credentials or member content into documentation examples.
5. Keep this repository private. Add collaborators only when they need access to the original methodology.

## Relationship to Cadence

Cadence Command Center implements selected workflows, schemas, prompts, and user experiences derived from these source materials. It does **not** make this repository a record of legal ownership, assignment, licensing, or authorship. Those determinations should be maintained in the applicable company records and agreements.
