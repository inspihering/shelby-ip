---
id: story-to-sales
version: 2026-09-28
sourceBasis:
  - source/story-to-sales/SKILL.md
  - source/story-to-sales/references/four-stories.md
  - source/story-to-sales/references/framework-naming.md
classification: proprietary-methodology
---

# Story-to-Sales Inference Layer

## Objective

Turn an expert’s verified lived experience, professional proof, audience understanding, and repeatable method into strategic stories that support a market position. The layer creates **business assets**, not a chronological autobiography.

## Inputs

```json
{
  "expert": {
    "name": "string",
    "role": "string",
    "voiceNotes": ["string"],
    "credentials": ["string"],
    "experience": ["string"],
    "pointOfView": ["string"]
  },
  "market": {
    "audience": "string",
    "audienceProblem": "string",
    "desiredTransformation": "string",
    "channels": ["keynote|website|one_sheet|podcast|social|sales_call|offer_page"]
  },
  "evidence": {
    "originMoments": ["string"],
    "credibilityProof": ["string"],
    "transformationMoments": ["string"],
    "clientProof": [{"context":"string","problem":"string","method":"string","result":"string","permission":"named|anonymized|unknown"}],
    "processSteps": ["string"]
  },
  "request": {
    "deliverable": "positioning|framework|story_bank|single_story|channel_copy",
    "storyTypes": ["origin|credibility|transformation|client"],
    "tone": "string"
  }
}
```

## Required reasoning sequence

1. **Establish the commercial context.** Identify the specific audience, felt problem, desired transformation, and requested channel. Do not draft a story before knowing what it must help the audience understand or buy.
2. **Separate facts from interpretation.** Treat supplied experience, credentials, outcomes, and client proof as facts. Treat framing and editorial language as interpretation. Never convert an inference into a factual claim.
3. **Choose only the relevant story types.** Use origin for why-the-work-matters; credibility for why-to-trust; transformation for personal wisdom connected to a professional method; client proof for evidence that the approach works beyond the expert.
4. **Find the process before naming it.** Look for repeated steps, a before/during/after arc, a 3–5-part method, or language the expert already uses. A framework must arise from perspective and practice, not a generic brand exercise.
5. **Form the position.** Populate: `I help [specific audience] solve [specific problem] so they can achieve [specific transformation] through [named approach].`
6. **Draft channel-appropriate assets.** Use the story format and length that match the requested placement. A keynote opening should not read like a sales-page case study.
7. **Run the story-quality test.** Every story must be relevant, evidence-based, useful to the audience, tied to authority or framework, and short enough to deploy.

## Story templates

| Type | Draft shape | Must prove |
|---|---|---|
| Origin | Background → recurring tension → core insight → current work | Why this work matters |
| Credibility | Experience/body of work → repeated pattern → developed approach → audience result | Why this expert is trustworthy |
| Transformation | Turning point → old belief → learned insight → changed practice → method | Why the expert’s perspective has depth |
| Client | Client context → problem/stakes → applied step → verified shift/result → proof point | Why the method works for others |

## Framework-naming decision policy

- Prefer an expert’s existing metaphors, phrasing, or point of view.
- Offer 2–3 name directions only after the process has been articulated.
- A name should suggest the transformation, be pronounceable, memorable, and expandable.
- Acronyms are allowed only when each letter maps naturally to a real component.
- Reject generic placeholders such as “my method,” “my approach,” or a forced acronym.

## Output contract

```json
{
  "status": "complete|needs_input|review_required",
  "positioningStatement": "string",
  "framework": {
    "nameOptions": ["string"],
    "recommendedName": "string|null",
    "description": "string",
    "components": ["string"],
    "rationale": "string"
  },
  "stories": [{
    "type": "origin|credibility|transformation|client",
    "draft": "string",
    "businessUse": ["string"],
    "evidenceUsed": ["string"],
    "reviewFlags": ["string"]
  }],
  "placementGuide": [{"channel":"string","recommendedStory":"string","reason":"string"}],
  "missingInputs": ["string"],
  "assumptions": ["string"],
  "reviewFlags": ["string"]
}
```

## Guardrails

- Never invent a client, credential, statistic, result, organization, testimonial, or personal turning point.
- Do not manufacture trauma, pressure disclosure, or confuse vulnerability with credibility.
- Do not produce generic hero’s-journey filler.
- Do not allow a story to become detached from the audience problem, authority, framework, or offer.
- Preserve the expert’s voice; polish for clarity without flattening distinctive language.

## Quality checks

A result is ready for review only if:

- the audience, problem, transformation, and method are specific;
- each story has a clear business purpose;
- all proof claims are traceable to supplied evidence;
- the framework reflects an actual repeatable process; and
- the reader can understand why the expert is relevant, credible, and referable.
