---
id: offer-architect
version: 2026-09-28
sourceBasis:
  - source/offer-architect/SKILL.md
classification: proprietary-methodology
---

# Offer Architect Inference Layer

## Objective

Convert expertise into a structured offer ecosystem that a buyer can understand, trust, invest in, and progress through. The layer distinguishes an expert’s raw knowledge from the **specific transformation, process, delivery, outcomes, and offer ladder** that make it marketable.

## Inputs

```json
{
  "expertise": {
    "knowledge": ["string"],
    "methodOrFramework": "string",
    "proof": ["string"],
    "problemsPeopleAskForHelpWith": ["string"]
  },
  "market": {
    "idealClient": "string",
    "clientStage": "string",
    "urgentProblem": "string",
    "desiredTransformation": "string"
  },
  "deliveryPreferences": {
    "formats": ["coaching|consulting|group|workshop|keynote|course|licensing|membership"],
    "accessLevel": "string",
    "timelinePreference": "string",
    "constraints": ["string"]
  },
  "existingBusiness": {
    "offers": ["string"],
    "assets": ["string"],
    "audienceChannels": ["string"]
  }
}
```

## Inference sequence

1. **Identify monetizable expertise.** Extract the recurring problem the expert can credibly solve, not merely the topic they know.
2. **Define the core transformation.** State the buyer’s current condition, desired condition, and the pathway between them.
3. **Design the core offer.** Define its audience, problem, promise, process, format, scope, inclusions, interaction model, and success evidence.
4. **Separate results.** Specify tangible outputs (assets, plans, systems, deliverables) and intangible shifts (clarity, confidence, authority, decision-making) without implying guaranteed outcomes.
5. **Set a realistic timeline.** Match duration to the depth of the claimed transformation and amount of implementation support.
6. **Choose delivery intentionally.** Decide where direct access, feedback, curriculum, templates, peer community, and boundaries are necessary.
7. **Map the ecosystem.** Propose only the ladder elements supported by the business: entry point, core transformation, internal client community, external community, premium offer, and continuity/membership.
8. **Validate commercial coherence.** Each layer should create a logical next step rather than unrelated products.

## Decision model

| Element | Must define | Common failure to prevent |
|---|---|---|
| Core offer | Buyer, urgent problem, transformation, method, format | Selling a vague category instead of a specific experience |
| Promise | Believable client result | Overpromising income or certainty |
| Tangible results | Assets, systems, decisions, or outputs | Confusing deliverables with transformation |
| Intangible results | Confidence, clarity, identity, authority | Using abstract emotional language without a business connection |
| Timeline | Phases, support needs, implementation time | Compressing a deep result into an unrealistic duration |
| Ladder | Purpose and handoff between offers | Creating random products with no progression |

## Output contract

```json
{
  "status": "complete|needs_input|review_required",
  "expertiseThesis": "string",
  "coreOffer": {
    "nameOptions": ["string"],
    "idealClient": "string",
    "problem": "string",
    "promise": "string",
    "positioningStatement": "string",
    "processPhases": [{"name":"string","purpose":"string","clientAction":"string"}],
    "format": "string",
    "duration": "string",
    "deliveryModel": ["string"],
    "inclusions": ["string"]
  },
  "results": {
    "tangible": ["string"],
    "intangible": ["string"],
    "successMeasures": ["string"]
  },
  "offerLadder": [{"tier":"entry|core|internal_community|external_community|premium|membership","purpose":"string","offerConcept":"string","handoff":"string"}],
  "assumptions": ["string"],
  "reviewFlags": ["string"]
}
```

## Guardrails

- Do not turn information alone into a sellable claim; name the buyer transformation and process.
- Do not promise revenue, client volume, or a guaranteed outcome without verified evidence and an approved claim policy.
- Do not invent prices, margins, capacity, testimonials, or delivery resources.
- Keep a distinction between one-time transformation, deeper advisory, community continuity, and premium customization.
- Treat recommendations as draft strategy, not binding operational or financial advice.

## Evaluation criteria

A strong output makes it possible to answer: **Who is this for? What urgent problem does it solve? What changes? How does the change happen? What does the client receive? Why does the format and timeline fit? What is the logical next step?**
