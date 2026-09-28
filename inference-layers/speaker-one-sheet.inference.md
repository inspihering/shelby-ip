---
id: speaker-one-sheet
version: 2026-09-28
sourceBasis:
  - source/speaker-one-sheet-builder/SKILL.md
  - source/speaker-one-sheet-builder/references/content-guide.md
  - source/speaker-one-sheet-builder/references/design-guide.md
classification: proprietary-methodology
---

# Speaker One-Sheet Inference Layer

## Objective

Produce the content strategy and visual-direction brief for a planner-first speaker one-sheet. The central test is whether an event planner can understand, in under 30 seconds, **who the speaker is, why they matter, what they deliver, who it fits, why they are credible, and how to book them**.

## Inputs

```json
{
  "speaker": {
    "name": "string",
    "title": "string",
    "positioning": "string",
    "brandVoice": "string",
    "brandSignals": ["string"],
    "photoAvailable": "boolean"
  },
  "audience": {
    "buyers": ["string"],
    "rooms": ["string"],
    "participants": ["string"],
    "problem": "string",
    "transformation": "string"
  },
  "keynotes": [{"title":"string","subtitle":"string","description":"string","takeaways":["string"],"bestFit":"string"}],
  "proof": {
    "credentials": ["string"],
    "organizations": [{"name":"string","permission":"confirmed|unknown"}],
    "testimonials": [{"quote":"string","source":"string","permission":"confirmed|unknown"}],
    "frameworks": ["string"]
  },
  "booking": {"email":"string","website":"string|null","phone":"string|null","reelUrl":"string|null","socials":["string"]}
}
```

## Reasoning sequence

1. Establish the positioning statement first. Every subsequent section must support the same audience, problem, transformation, and perspective.
2. Select one **anchor keynote**. Additional topics support the anchor; they do not compete with it.
3. Create planner-facing content blocks: best-fit buyers/rooms, keynote promise, 3–4 action-oriented takeaways, short bio, credibility snapshot, supported organizations/testimonials, and booking CTA.
4. Use only permission-confirmed organizations and logo claims. If proof is thin, use an industry framing or omit the section.
5. Choose a visual direction that reflects the speaker’s actual point of view, not a generic corporate template.
6. Allocate hierarchy and white space. Strong positioning and the signature keynote should be the dominant elements.
7. Generate a content brief suitable for PDF/Word production, but preserve a human approval step before publication.

## Content decision rules

| Block | Requirement | Reject when |
|---|---|---|
| Positioning strip | Specific audience + problem + transformation + perspective | A competitor could claim it unchanged |
| Best-fit audiences | 4–7 credible buyer/room types | It lists every possible industry |
| Signature keynote | Point-of-view title, promise, 100–150-word planner description, 3–4 concrete takeaways | It is a generic topic label or speaker-centered biography |
| Bio | Identity → signature message → selected proof → audience result | It reads as a résumé |
| Credibility snapshot | 5–7 relevant proof lines | It includes unrelated accomplishments |
| Testimonial | Permissioned, specific, concise proof | It is invented, generic, or unverified |
| Booking bar | Direct CTA plus available contact channels | Booking path is missing or ambiguous |

## Output contract

```json
{
  "status": "complete|needs_input|review_required",
  "contentBrief": {
    "positioningStatement": "string",
    "brandStatement": "string",
    "bestFitAudiences": ["string"],
    "signatureKeynote": {"title":"string","subtitle":"string","description":"string","takeaways":["string"]},
    "supportingTopics": [{"title":"string","description":"string","bestFit":"string","takeaways":["string"]}],
    "shortBio": "string",
    "credibilitySnapshot": ["string"],
    "organizationsSection": "string|null",
    "testimonialSelections": [{"quote":"string","source":"string"}],
    "bookingCta": "string"
  },
  "designDirection": {
    "mood": "string",
    "colorDirection": "string",
    "typeDirection": "string",
    "signatureVisualDevice": "string",
    "layoutPriority": ["string"],
    "missingAssetTreatment": ["string"]
  },
  "evidenceNeeded": ["string"],
  "reviewFlags": ["string"]
}
```

## Guardrails

- A one-sheet is not a résumé.
- Never invent logos, organizations, credentials, testimonials, media placements, or client results.
- Do not use generic “empowering,” “passionate,” or “transformative journey” language as the core value claim.
- Do not make every one-sheet visually identical; visual direction should follow positioning.
- Keep actual output assets separate: the inference layer produces a brief; a rendering service creates PDF and editable Word versions.

## Quality test

A reviewer should be able to scan the result and immediately answer: **What room is this speaker best for? What will the audience gain? Why should this person be trusted? What is the keynote? How do I book them?**
