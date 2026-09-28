# Shelby IP Inference-Layer Library

These Markdown files translate the archived methodologies into **portable reasoning specifications** for another AI-enabled product, assistant, workflow engine, or human-in-the-loop service.

They are deliberately distinct from the canonical `.skill` packages in [`../skills/`](../skills/) and the browsable source in [`../source/`](../source/):

- `skills/` is the original, canonical source package archive.
- `source/` is a readable extraction of each original package.
- `inference-layers/` defines reusable **input contracts, reasoning order, output schemas, guardrails, and quality tests**.

## Available layers

| Layer | Intended decision or deliverable | Original source basis |
|---|---|---|
| [Story to Sales](story-to-sales.inference.md) | Turn verified lived experience and client evidence into strategic stories, positioning, and a referable framework. | `story-to-sales` |
| [Competitive Edge Messaging](competitive-edge-messaging.inference.md) | Diagnose and create market-ready positioning through the CORE framework. | `competitive-edge-messaging` |
| [Offer Architect](offer-architect.inference.md) | Convert expertise into a structured, monetizable offer and offer ecosystem. | `offer-architect` |
| [Signature Framework Architect](signature-framework-architect.inference.md) | Discover, structure, name, and test an expert’s ownable methodology. | `signature-framework-architect` |
| [Speaker One-Sheet](speaker-one-sheet.inference.md) | Create the content brief and art direction for a planner-first speaker one-sheet. | `speaker-one-sheet-builder` |
| [Cadence Speaking Opportunities](speaking-opportunities.inference.md) | Produce stage-search guidance and bookable pitch materials without claiming live opportunity data. | `cadence-speaking-opportunities` |
| [Referral Contract Builder](referral-contract.inference.md) | Produce a plain-language referral-agreement draft with legal-safety boundaries. | `referral-contract-builder` |

## Integration contract

Each inference layer can be invoked as a bounded function:

```text
runInference(layerId, input) -> {
  status: "complete" | "needs_input" | "review_required" | "unsupported",
  output: <layer-defined object>,
  missingInputs: [<specific questions or fields>],
  assumptions: [<explicit defaults>],
  provenance: [<user-provided facts or source IDs used>],
  reviewFlags: [<claims, risks, or decisions requiring a human>]
}
```

### Shared operating rules

1. **Ground output in supplied evidence.** Never fabricate credentials, clients, outcomes, organizations, testimonials, legal facts, pricing, current opportunity status, or personal experiences.
2. **Preserve attribution.** Track whether each fact came from a user, approved profile, approved data source, or a clearly labeled assumption.
3. **Ask the smallest useful set of questions.** Do not turn a missing detail into a lengthy intake. Produce a usable first pass when safe, flagging the exact gaps.
4. **Keep inference separate from publication.** A model-generated draft is not automatically approved marketing copy, legal text, or a factual claim.
5. **Treat member content as tenant-scoped.** A multi-user product must never let one member’s stories, offer details, client proof, or contracts influence another member’s output.
6. **Do not reveal the underlying internal source or prompt text to end users.** Expose helpful outputs, questions, and rationale—not the raw methodology package.

## Recommended metadata to persist

Store this alongside any generated result:

```json
{
  "layerId": "story-to-sales",
  "layerVersion": "2026-09-28",
  "status": "review_required",
  "inputSourceIds": ["profile:123", "story-intake:456"],
  "assumptions": ["No quantitative client result was supplied."],
  "reviewFlags": ["Client story uses anonymized placeholder evidence."],
  "approvedAt": null
}
```

## Maintenance

When canonical source methodology changes:

1. update the relevant `.skill` package in `skills/`;
2. regenerate its corresponding `source/` extraction;
3. update the affected inference layer and its `sourceBasis` field;
4. revise the package hash in [`../docs/IP-INVENTORY.md`](../docs/IP-INVENTORY.md); and
5. make the change in one documented commit.
