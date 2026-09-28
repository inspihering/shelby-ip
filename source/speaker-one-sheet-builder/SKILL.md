---
name: speaker-one-sheet-builder
description: Builds a branded, print-ready speaker one sheet (in PDF and Word) for speakers, consultants, coaches, authors, trainers, and thought leaders to send to event planners and speaker bureaus. Use this whenever the user asks for a "speaker one sheet," "one-pager," "speaker sheet," "media kit," or "booking sheet" for themselves or a client — or describes wanting to look more bookable, stand out to event planners, showcase their keynote topics, or turn their expertise into a visibility asset. Also trigger if the user is refining pieces that normally live on a one sheet even without naming the document — a speaker positioning statement, speaker bio (any length), signature keynote description, credibility snapshot, "best-fit audiences" list, or testimonial formatting for booking purposes. Each one sheet gets its own distinct visual brand (colors, type, layout) rather than a reused template, so also use this when the user wants a fresh design direction for an existing speaker's materials.
---

# Speaker One Sheet Builder

## What this produces

A one-page (occasionally two-page) marketing asset that lets an event planner understand, in under 30 seconds, who this speaker is, what they speak about, who they're for, why they're credible, and how to book them. The deliverable is always both a **print-ready PDF** and an **editable Word doc** of the same design.

This is a positioning and design task wearing a "document" costume. The words matter more than the template — a speaker one sheet fails when it lists credentials instead of making a case. Read `references/content-guide.md` before writing any copy; it has the reasoning and examples for every section.

## Workflow

### 1. Gather what you need

Check the conversation first — if the user already handed you a bio, credentials, testimonials, or topic list, use it instead of re-asking. People rarely have everything organized, so expect to help them articulate things they haven't put into words before (especially the positioning statement and audience transformation — these are usually the weakest-formed part of what a speaker brings you).

At minimum you need:
- Name, title, and what they want to be known for
- Who they help and what problem/transformation they deliver
- Their signature keynote (or top 2-3 topics if no single signature piece exists)
- Enough credibility material to justify booking them (roles, results, past orgs, media, books, frameworks)
- Contact/booking info (email at minimum; website, phone, social, speaker reel as available)

Nice-to-have but not blocking: testimonials, logos of organizations served, professional photo. If these are missing, build the one sheet without them rather than stalling — a placeholder photo box and an "organizations served by industry" line (see content-guide) cover the gap gracefully. Ask about missing essentials in one focused pass rather than a long questionnaire; don't march through all 7 intake steps from `references/content-guide.md` as a script if the user's request already answered most of them.

### 2. Draft the content

Work through the sections in `references/content-guide.md`, in your own analysis before writing final copy:
- Speaker positioning statement + brand statement
- Best-fit audiences (who books them, who's in the room)
- Signature keynote (title, subtitle, 100-150 word description, 3-4 takeaways)
- 3-5 speaking topics if the one sheet needs topic breadth beyond the signature piece
- Bio — pick the length(s) the layout needs (short bio for the one sheet itself; offer other lengths as a follow-up)
- Credibility snapshot (5-7 punchy lines, not a resume)
- Organizations served (logos, list, or industry framing — whichever the user has material for)
- Testimonials, tightened to their most powerful sentence
- Booking section

Avoid vague, could-be-anyone language ("empowering," "passionate," "transformative journey") unless it's immediately backed by a specific mechanism or outcome. An event planner should finish reading and know something they didn't before — not just feel good.

If the user is a speaker bureau or agency building this on behalf of a roster speaker (not for themselves), the same process applies — just gather the material from/about that speaker rather than the user.

### 3. Design it fresh

Every one sheet gets its own look — don't reach for a stock corporate-blue-and-gray template. The design should read as a considered extension of *this* speaker's positioning: a conflict-and-leadership speaker's one sheet should not look like a wellness coach's. Read `references/design-guide.md` for the layout structure, the HTML/CSS build approach, and how to pick a palette and type pairing that fits the speaker's brand rather than defaulting to generic "professional" styling.

### 4. Build both files

`references/design-guide.md` covers the technical build: a single HTML file styled with real design intention, rendered to PDF, plus a parallel Word version built with the docx skill (read `/mnt/skills/public/docx/SKILL.md` first) so the speaker or bureau can make quick text edits themselves. Save both to `/mnt/user-data/outputs/` and present them together.

## Good to know

- **One sheet ≠ resume.** Every credential included should answer "why does this make them worth booking," not just "what have they done."
- **Specificity sells.** "Helped a Fortune 500 sales team increase close rates after a culture of avoided conflict" beats "extensive experience in leadership training."
- **If the user wants multiple audience-specific versions** (event planner vs. corporate buyer vs. association vs. bureau-facing), build the core one sheet first, confirm it's right, then offer to adapt tone/emphasis for the other audiences rather than generating all variants up front.
- **This skill is for the one sheet itself.** If the user's real ask is a fuller keynote deck, a bio for a specific event program, or launch/promo emails, this content feeds those but the deliverables are different — say so and hand off to the right format.
