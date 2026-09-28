---
id: signature-framework-architect
version: 2026-09-28
sourceBasis:
  - source/signature-framework-architect/SKILL.md
classification: proprietary-methodology
---

# Signature Framework Architect Inference Layer

## Objective

Transform an expert’s own perspective, recurring methodology, and verified results into a named framework that is **memorable, repeatable, referable, teachable, and brandable**. The framework must reflect how the expert actually creates transformation—not be a decorative acronym.

## Inputs

```json
{
  "expert": {
    "credentials": ["string"],
    "experience": ["string"],
    "recurringAdvice": ["string"],
    "languageAndMetaphors": ["string"],
    "beliefs": ["string"],
    "casePatterns": ["string"]
  },
  "market": {
    "audience": "string",
    "surfaceProblem": "string",
    "underlyingDesire": "string",
    "beforeState": "string",
    "afterState": "string"
  },
  "method": {
    "steps": ["string"],
    "principles": ["string"],
    "recurringDecisions": ["string"],
    "evidence": ["string"]
  },
  "request": {"useCase":"positioning|keynote|offer|diagnostic|curriculum|content"}
}
```

## Two-phase reasoning model

### Phase 1 — Own It

1. Identify knowledge, experience, perspective, and methodology; give most weight to **perspective plus methodology**, not credentials alone.
2. Extract a point of view using one of these forms:
   - `Most people believe [x]. I believe [y] because [evidence].`
   - `The real problem is not [x]; it is [y].`
   - `You do not need more [x]; you need [y].`
3. Define the audience’s before state, underlying desire, and after state.
4. Identify the ownable idea: the concept an audience should associate with the expert’s name.
5. Test that territory for relevance, evidence, distinction, memorability, and expandability.

### Phase 2 — Name It

1. Extract 3–7 real components from the method; four or five often provides useful teaching granularity.
2. Select an architecture that matches the mechanism:

| Architecture | Use when |
|---|---|
| Sequential | The work happens in a reliable order |
| Pillar | Multiple principles must coexist |
| Cycle | The process repeats continuously |
| Matrix | Two dimensions explain diagnostic categories |
| Pyramid | Foundational conditions support higher outcomes |
| Journey | Identity or stage changes over time |
| Diagnostic/maturity model | The expert first determines current state |
| Ecosystem | Components are interdependent |

3. Generate naming directions: descriptive, outcome-based, conceptual, acronym, metaphorical, identity-based, or branded process.
4. Score names for pronunciation, recall, spelling, transformation relevance, market appropriateness, distinctiveness, and product expandability.
5. Name components with linguistic consistency only when it remains natural. Clarity outranks a clever forced acronym.

## Output contract

```json
{
  "status": "complete|needs_input|review_required",
  "intellectualTerritory": {
    "pointOfView": "string",
    "ownableIdea": "string",
    "beforeAfter": {"before":"string","after":"string","approach":"string"}
  },
  "framework": {
    "recommendedArchitecture": "string",
    "architectureRationale": "string",
    "components": [{"name":"string","function":"string","evidence":"string|null"}],
    "nameDirections": [{"category":"string","options":["string"]}],
    "recommendedName": "string|null",
    "description": "string"
  },
  "marketTest": {
    "relevant": "boolean",
    "distinctive": "boolean",
    "memorable": "boolean",
    "expandable": "boolean",
    "gaps": ["string"]
  },
  "reviewFlags": ["string"]
}
```

## Guardrails

- Do not start naming before the transformation and actual mechanism are understood.
- Never present a borrowed, generic, or unsupported concept as the expert’s proprietary method.
- Do not force an acronym or a fixed number of components.
- Do not make claims about trademark availability, legal ownership, or market uniqueness without separate legal or trademark review.
- Keep the framework grounded in the expert’s documented language, perspective, and practice.

## Acceptance test

A framework is ready to review when a listener can say: **“This is the person who teaches [ownable idea], through [named method], to help [audience] move from [before] to [after].”**
