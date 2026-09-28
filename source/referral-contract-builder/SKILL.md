---
name: referral-contract-builder
description: Builds a plain-language referral agreement/contract that an entrepreneur, coach, consultant, speaker, or service provider can use with another business owner to formalize a referral partnership. Use this whenever the user asks to draft, create, or update a "referral agreement," "referral contract," "referral partner agreement," "affiliate/referral terms," or wants to define a referral fee, commission split, or payout terms with another business. Also trigger for related setup questions like "what referral fee should I offer," "how do I structure a referral partnership," or "help me formalize a referral relationship with [person/business]." This skill is specifically for the written agreement/contract deliverable — not for general referral-partner prospecting, tracking spreadsheets, or marketing copy (though it can point to those as follow-ups).
---

# Referral Contract Builder

Helps a solo entrepreneur or small business owner turn a referral relationship into a clear, written agreement with another business owner — the deliverable is a finished contract/agreement document, not a full referral-marketing program.

## Scope

In scope: intake, referral fee/commission structuring, and drafting the actual referral agreement as a document.
Out of scope (mention briefly as a possible follow-up, don't build unless asked): referral-partner prospecting lists, tracking spreadsheets/CRMs, invitation emails, social posts, launch plans for a referral group. If the user wants one of those, note you can help with it separately.

## Workflow

### 1. Gather the essentials

Don't stall on missing info — ask only for what's needed to draft a usable contract, and offer sensible defaults for anything the user doesn't specify (flag defaults clearly in the draft so they can adjust). Needed inputs:

- **Both parties**: names, business names, and roles (who is referring, who is being referred to — or is it mutual/two-way?)
- **What's being referred**: the specific offer(s)/service(s) eligible for referral, brief description, price point
- **Qualified referral definition**: what counts as a valid referral (e.g., must book a call, must become a paying client)
- **Fee structure**: flat fee, % of first sale, % of recurring revenue for a defined period, or tiered — see `references/fee-guidance.md` for typical ranges by offer type if the user needs help choosing
- **Payment terms**: when the fee is earned (e.g., on signed contract, on payment clearing) and when it's paid (e.g., net 15 after client payment clears)
- **Recurring vs. one-time**: does the referral fee apply only to the first purchase, or to future/recurring revenue, and for how long
- **Refunds/cancellations**: whether refunds or chargebacks claw back the referral fee
- **Term & termination**: how long the agreement runs, how either party can end it
- **Non-circumvention**: whether either party agrees not to go around the other to deal with a referred client directly

If the user gives a quick, casual description ("I want to pay Jane 15% for the first year on anyone she sends me"), extract everything you can from that and only ask about genuine gaps.

### 2. Draft the agreement

Use `references/agreement-clauses.md` for the full clause list and standard plain-language wording patterns. Structure the document with these sections in order:

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

Always include this disclaimer near the top or bottom of the document, unmodified:

> This is a business draft and not legal advice. Please have this agreement reviewed by a qualified attorney before using it with referral partners.

### 3. Output format

Default to a Word document (.docx) since this is a signable business contract — read `/mnt/skills/public/docx/SKILL.md` before creating it, and use its formatting guidance (headings, numbered sections, signature block). If the user just wants to see the language first or asks for something quick/inline, draft it in the chat or as markdown, then offer to turn it into a polished .docx for signing.

### 4. Tone and guardrails

- Don't guarantee income or frame the fee as "passive" — it's a negotiated business term.
- Don't give legal advice as if you were an attorney; the disclaimer covers this, but also avoid asserting that specific clauses are "enforceable" or "compliant" in the user's jurisdiction.
- Flag if the referred offer is in a regulated space (financial, legal, medical, insurance) where referral-fee disclosure rules may apply, and note they should confirm requirements with an attorney or compliance advisor — don't try to resolve this yourself.
- Encourage written terms over a handshake deal, and encourage clear tracking (a simple line: "each party will log referrals in [tool/spreadsheet] within X days") even if a full tracking system isn't being built here.
- Keep the language strategic and clear, not vague or overly corporate — this is a working document two business owners will actually sign and use.

## Suggested fee ranges (for reference only)

See `references/fee-guidance.md` for typical ranges by offer type (low-ticket digital product, workshop/event, coaching/consulting, high-ticket program, membership, corporate/speaking). Use these only as a starting anchor — the right number depends on profit margin, sales cycle length, delivery cost, and how much work the referral partner does to close the sale.
