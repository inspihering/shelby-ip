# Shelby IP Source Inventory

**Inventory date:** September 28, 2026
**Archive purpose:** Preserve owner-designated original source materials separately from Cadence application code.

The SHA-256 values below record the exact source files copied into this archive. Recalculate the relevant hash whenever a source artifact changes.

| Source artifact | SHA-256 | Cadence relationship |
|---|---|---|
| `skills/cadence-speaking-opportunities.skill` | `4b0d59eb789d29307d21cefb3b7ed2af6c560285b951aad837f590c6c2e8948b` | Informs the speaking-opportunity product domain. Cadence reads finalized match data from Airtable; it does not contain the upstream matching methodology itself. |
| `skills/competitive-edge-messaging.skill` | `3591f1c9e6280611dcbf4a6f04f2e9edcdb498a7f713d0f0739e1b3f2705cbd6` | Informs positioning and messaging-oriented workflow structure. |
| `skills/offer-architect.skill` | `95db3e9252ce1fab9f7ea802434cfaa5d57142a0aecb7ad46879646eb36d30f8` | Informs offer and business-offer workflow concepts used in Keynotes Studio. |
| `skills/referral-contract-builder.skill` | `3ee7f32e2a6a820bd3b546dc74726d92491d544e820bb564cdc24d79e4a2341f` | Preserved as source material; no claim is made here about its current Cadence implementation coverage. |
| `skills/signature-framework-architect.skill` | `48ee11978f0931474fb55087cbb3a9e81eaa1c142d638f93207da8759a78691d` | Informs framework-selection concepts used in Strategy Lab and Keynotes Studio. |
| `skills/speaker-one-sheet-builder.skill` | `c88eab019489acceffd0289b2e1eb0430cb0f94c8ce00683d593a09bf020c1ea` | Informs the speaker one-sheet composer and document-export product area. |
| `skills/story-to-sales.skill` | `18d00e9e2042a8bb361c37ebb6ba951cda84376901cfc754274a93fdaec2663a` | Informs story-source and strategy-workflow concepts used in Keynotes Studio. |

## Implementation boundary

The private `cadence-command-center` repository contains the application code that implements selected product behavior. This archive preserves the original source artifacts separately, so the methodology can be reviewed and evolved without coupling it to deployment code.

The following material is intentionally outside both code repositories unless separately archived:

- member-created workspace content;
- Airtable records and upstream Airtable → Claude → Make matching logic;
- GHL, Rubic, Resend, Supabase, and Manus credentials or settings exports;
- legal agreements establishing ownership, licenses, or assignments.
