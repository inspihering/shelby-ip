---
id: competitive-edge-messaging
version: 2026-09-28
sourceBasis:
  - source/competitive-edge-messaging/SKILL.md
  - source/competitive-edge-messaging/references/core-framework.md
  - source/competitive-edge-messaging/references/formulas.md
  - source/competitive-edge-messaging/references/messaging-rules.md
classification: proprietary-methodology
---

# Competitive Edge Messaging Inference Layer

## Objective

Transform verified offer and audience information into clear, differentiated, market-ready messaging through the **CORE** sequence: **Clarity, Ownership, Relevance, Engagement**.

## Inputs

```json
{
  "offer": {
    "name": "string",
    "format": "string",
    "description": "string",
    "process": "string",
    "evidence": ["string"]
  },
  "audience": {
    "segment": "string",
    "feltProblem": "string",
    "language": ["string"],
    "stakes": "string",
    "desiredOutcome": "string"
  },
  "expert": {
    "credibility": ["string"],
    "livedExperience": ["string"],
    "pointOfView": "string",
    "framework": "string"
  },
  "request": {
    "deliverable": "positioning|tagline|bio|hero_copy|offer_copy|keynote|sales_script|thought_leadership",
    "channel": "string",
    "voice": "string"
  }
}
```

## CORE reasoning protocol

| Stage | Infer | Required question |
|---|---|---|
| **C — Clarity** | Offer, specific buyer, felt problem, promised outcome | Can a buyer explain the value quickly? |
| **O — Ownership** | Credibility, lived experience, distinct belief, named framework | Why this expert rather than any qualified competitor? |
| **R — Relevance** | Current buyer language, stakes, priorities, emotional and practical need | Does the audience recognize themselves in the message? |
| **E — Engagement** | Appropriate invitation, content angle, CTA, or next step | What should the right person do next? |

### Required sequence

1. Normalize the offer into a specific buyer-facing description.
2. State the audience problem in the audience’s own language—not service-provider jargon.
3. Articulate the transformation as a concrete change in capability, decision, identity, or business outcome.
4. Identify ownership evidence: a real perspective, body of work, framework, or experience.
5. Identify a meaningful contrast. “Unique,” “innovative,” and “passionate” are adjectives, not differentiation.
6. Generate the requested deliverable using the relevant formula.
7. Test for interchangeability: if a direct competitor could use the copy unchanged, revise it.

## Formula library

### Positioning

> I help **[specific audience]** solve **[specific problem]** so they can achieve **[specific transformation]** through **[unique process, framework, or approach]**.

### Brand story

`Before → Turning point → Discovery → Credibility → Mission → Transformation`

### Offer message

`This [offer] helps [audience] move from [current struggle] to [desired outcome] by guiding them through [process]. By the end, they have [tangible result], [intangible result], and [strategic benefit].`

### Thought leadership

`Common belief → contrary perspective → stakes → practical application → invitation`

## Output contract

```json
{
  "status": "complete|needs_input|review_required",
  "coreDiagnosis": {
    "clarity": {"strengths":["string"],"gaps":["string"]},
    "ownership": {"strengths":["string"],"gaps":["string"]},
    "relevance": {"strengths":["string"],"gaps":["string"]},
    "engagement": {"strengths":["string"],"gaps":["string"]}
  },
  "positioning": "string",
  "messagePillars": [{"claim":"string","support":"string","audienceRelevance":"string"}],
  "deliverables": [{"type":"string","draft":"string","cta":"string|null"}],
  "alternatives": [{"label":"string","draft":"string"}],
  "evidenceNeeded": ["string"],
  "reviewFlags": ["string"]
}
```

## Guardrails

- Specificity beats cleverness.
- Do not claim an outcome, credential, market position, client result, or expertise that is not supplied.
- Do not lead with credentials before naming the buyer problem and transformation.
- Do not assume the audience is “everyone.”
- Avoid generic phrases as the primary claim: “level up,” “unlock potential,” “transform your life,” or “take your business to the next level.”
- Preserve supplied voice and wording where it adds distinction.

## Acceptance test

The output passes when a target buyer can identify: **who it is for, what painful situation it addresses, what changes, why this expert is credible, what is distinct, and what to do next**.
