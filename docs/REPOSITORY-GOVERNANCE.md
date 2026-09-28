# Shelby IP Archive Governance

## Access boundary

This is a private source archive. Access should be limited to people who need the underlying methodology, not simply people who need to work on Cadence application code. The Cadence application repository remains a separate private repository so engineering access and methodology access can be granted independently.

## Change control

Each change to a source skill should use one commit or pull request that states:

1. the source artifact changed;
2. the substantive framework or process change;
3. the affected Cadence workflow, if any; and
4. whether a corresponding implementation change is required in `cadence-command-center`.

Do not overwrite a source skill without preserving its Git history. If a major redesign is intended, create a new skill file or clearly describe the version change in the commit message.

## Integrity record

`docs/IP-INVENTORY.md` contains the baseline SHA-256 value for each archived artifact. A changed hash is expected only after a deliberate change. Recalculate it with:

```bash
sha256sum skills/<filename>.skill
```

Then update the inventory in the same commit.

## Prohibited content

Never commit:

- API keys, access tokens, private keys, passwords, or environment files;
- member, buyer, applicant, speaker, or staff personal data;
- payment data or webhook payload logs;
- database exports; or
- production-service configuration exports.

## Ownership and legal records

This archive is an engineering evidence trail and version-control system. It does not itself establish ownership, authorship, work-for-hire status, trademarks, licenses, or assignments. Maintain those legal determinations in the appropriate company agreements and records.
