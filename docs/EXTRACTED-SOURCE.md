# Browsable Source Extraction

The canonical original packages remain unchanged in `skills/*.skill`.

Because `.skill` files are ZIP-based packages and GitHub does not render their internal Markdown in the file browser, `source/` is an exact, browsable extraction of the text and reference files inside those packages. It exists for review and version history; it is not an independently edited second source.

## Review rule

- **Canonical package:** `skills/<name>.skill`
- **Browsable representation:** `source/<package-directory>/...`
- If a skill changes, update the canonical package first, recreate its corresponding `source/` extraction, and update the package hash in `docs/IP-INVENTORY.md` in the same commit.

## Included methodology

The extracted files include actual frameworks, workflows, prompt guardrails, structure guides, design guidance, formula references, and output expectations—not merely titles or filenames.
