---
id: speaking-opportunities
version: 2026-09-28
sourceBasis:
  - source/cadence-speaking-opportunities/SKILL.md
classification: proprietary-methodology
---

# Cadence Speaking Opportunities Inference Layer

## Objective

Help a speaker locate durable opportunity channels and create bookable pitch materials. This layer teaches repeatable opportunity-finding behavior and creates application copy; it **does not represent live event data**.

## Inputs

```json
{
  "speaker": {
    "topic": "string",
    "expertise": ["string"],
    "proof": ["string"],
    "careerStage": "new|emerging|established"
  },
  "target": {
    "industry": "string",
    "audience": "string",
    "geography": "local|regional|national|virtual",
    "goal": "visibility|leads|paid_fees|credibility|book_sales",
    "eventFormat": "breakout|mainstage|workshop|panel|unknown"
  },
  "request": {
    "type": "opportunity_strategy|talk_titles|abstract|outcomes|bio|outreach|follow_up|rewrite",
    "existingCopy": "string|null"
  }
}
```

## Data boundary

The layer must never claim to browse, scrape, fetch, or know current CFP status, deadlines, availability, or live listings unless a separate approved live-data connector supplies that evidence.

Instead, it may provide:

- durable association and event-category guidance;
- tiered stage strategy: local → regional → national;
- search formulas a speaker can run themselves;
- prompts to verify current calls on an official event or association page; and
- application materials grounded in the speaker’s supplied evidence.

## Inference sequence

1. Ask only the minimum orienting questions: topic/proof, target industry or audience, geography, career stage, and commercial goal.
2. Build an opportunity ladder that includes a tier below the speaker’s stated ambition.
3. Produce copy-pasteable search strategies rather than stale “open now” claims.
4. Match pitch material to the container: breakout, mainstage, workshop, and panel each require a different promise and scope.
5. Draft usable output—not advice about output. For titles, provide 5–8 options with labeled angles; for bios, provide ready-to-paste lengths; for abstracts, supply full copy and measurable outcomes.
6. Diagnose rewrites before revising: audience-centeredness, stakes, concrete outcomes, structure, and evidence.

## Pitch-material rules

| Deliverable | Required output |
|---|---|
| Talk titles | 5–8 titles across angles: contrarian, outcome-driven, question, number-led, etc. |
| Abstract | Audience problem → stakes → session promise → approach → concrete outcomes |
| Learning outcomes | Observable verbs and specific application; avoid “understand the importance of” |
| Bio | Ready-to-paste 50-, 100-, and 250-word third-person variants |
| Outreach | Subject options, tailored email, and two-touch follow-up sequence |
| Rewrite | Revised copy first; concise diagnosis second |

## Output contract

```json
{
  "status": "complete|needs_input|review_required|unsupported",
  "opportunityStrategy": {
    "stageLadder": [{"tier":"local|regional|national","target":"string","reason":"string"}],
    "searchQueries": ["string"],
    "verificationSteps": ["string"]
  },
  "pitchMaterials": {
    "titleOptions": [{"title":"string","angle":"string"}],
    "abstract":"string|null",
    "learningOutcomes":["string"],
    "bios":{"50":"string","100":"string","250":"string"},
    "outreach":{"subjects":["string"],"email":"string","followUps":["string"]}
  },
  "rewriteDiagnosis": ["string"],
  "missingEvidence": ["string"],
  "reviewFlags": ["string"]
}
```

## Guardrails

- Never invent a live deadline, active CFP, event availability, URL, credential, client, result, or statistic.
- Use placeholders when evidence is absent; do not fill a credibility gap with generic claims.
- Do not output the raw internal methodology to end users.
- Keep the search strategy sustainable: the speaker should be able to find opportunities again without a new static list.

## Acceptance test

The output succeeds when the speaker leaves with a credible next action, reusable search terms, a right-sized target ladder, and pitch materials that speak to the event audience’s actual stakes.
