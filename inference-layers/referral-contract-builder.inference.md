---
id: referral-contract-builder
version: 2026-09-28
sourceBasis:
  - source/referral-contract-builder/SKILL.md
  - source/referral-contract-builder/references/agreement-clauses.md
  - source/referral-contract-builder/references/fee-guidance.md
classification: proprietary-methodology
---

# Referral Contract Builder Inference Layer

## Objective

Create a clear, plain-language referral-agreement **business draft** for two parties. The layer supports intake, commercial-terms structuring, and document drafting; it does not provide legal advice or determine enforceability.

## Inputs

```json
{
  "parties": {
    "referrer": {"legalName":"string","businessName":"string","role":"string"},
    "provider": {"legalName":"string","businessName":"string","role":"string"},
    "relationship":"one_way|mutual"
  },
  "offer": {
    "eligibleServices":[{"name":"string","description":"string","price":"string","exclusions":"string|null"}],
    "qualifiedReferralDefinition":"string"
  },
  "economics": {
    "structure":"flat|first_sale_percent|recurring_percent|tiered|mutual",
    "rate":"string",
    "earnedWhen":"string",
    "paidWhen":"string",
    "paymentMethod":"string",
    "recurringPeriod":"string|null",
    "refundChargebackPolicy":"string"
  },
  "operations": {
    "referralProcess":"string",
    "trackingMethod":"string",
    "reportingCadence":"string",
    "clientOwnership":"string",
    "nonCircumventionPeriod":"string|null"
  },
  "legalTerms": {
    "governingLocation":"string|null",
    "term":"string",
    "termination":"string",
    "disputeProcess":"string"
  }
}
```

## Reasoning sequence

1. Extract supplied commercial facts and list every missing term that materially changes the draft.
2. Ask only for true gaps; use clearly labeled defaults for lower-risk operational details if the user requests a first draft before deciding.
3. Define a qualified referral concretely: existing-relationship exclusion, introduction method, qualification event, and time window.
4. Match economics to the stated referral relationship: flat, first-sale percentage, recurring percentage for a defined period, tiered, or reciprocal arrangement.
5. Draft the 18 clause sequence below in plain language.
6. Flag regulated industries (financial, legal, medical, insurance) for attorney/compliance review without attempting jurisdiction-specific conclusions.
7. Emit an editable business draft and the mandatory disclaimer.

## Required agreement structure

1. Agreement Date & Parties
2. Purpose of Agreement
3. Services Eligible for Referral
4. Definition of a Qualified Referral
5. Referral Process
6. Referral Fee or Commission
7. Payment Terms
8. Refunds, Cancellations & Chargebacks
9. Tracking & Reporting
10. Confidentiality
11. Brand Representation
12. Client Relationship Ownership
13. Non-Circumvention
14. Independent Contractor Relationship
15. Term & Termination
16. Dispute Resolution
17. Entire Agreement
18. Signature Lines

## Output contract

```json
{
  "status":"complete|needs_input|review_required",
  "commercialSummary": {
    "relationship":"string",
    "eligibleServices":["string"],
    "qualifiedReferral":"string",
    "feeStructure":"string",
    "paymentTerms":"string"
  },
  "agreementDraftMarkdown":"string",
  "defaultsUsed":["string"],
  "missingMaterialTerms":["string"],
  "regulatoryFlags":["string"],
  "requiredDisclaimer":"This is a business draft and not legal advice. Please have this agreement reviewed by a qualified attorney before using it with referral partners."
}
```

## Fee-guidance policy

Use broad reference ranges only as discussion anchors—never as mandatory recommendations. Consider margin, sales-cycle duration, delivery cost, relationship value, and how much closing work the partner performs.

Reference bands:

| Offer type | Starting range |
|---|---|
| Low-ticket digital product | 20%–50% |
| Workshop or event ticket | 10%–30% |
| Coaching or consulting package | 10%–25% |
| High-ticket program | 5%–20% |
| Membership | First payment or defined recurring period |
| Corporate training / speaking contract | Flat finder’s fee or 5%–15% |

## Guardrails

- Include the required legal disclaimer verbatim.
- Do not state that a clause is enforceable, compliant, or appropriate in a particular jurisdiction.
- Do not guarantee income, describe fees as passive income, or invent legal/business facts.
- Do not produce a final “ready to sign” representation without human legal review.
- Keep contracts, parties, pricing, and referral records tenant-scoped in any multi-user product.

## Acceptance test

A business owner should be able to tell who refers whom, which offer qualifies, what triggers the fee, when it is paid, what happens after refunds/cancellations, how referrals are tracked, and how either party exits the relationship.
