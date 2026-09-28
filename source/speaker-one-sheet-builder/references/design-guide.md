# Design & Build Guide

## Layout structure

A standard one-page layout, top to bottom (adjust proportions to content, not every section needs equal weight):

1. **Header band** — name, professional title, tagline, photo (or a styled placeholder box if none provided), booking contact line
2. **Positioning strip** — one strong sentence: who they help, what problem, what transformation. This is often reversed out of a color block so it reads as the "headline," not body text.
3. **Signature keynote** — title, subtitle, description, takeaways (this is usually the largest content block; it's the offer)
4. **Speaking topics** — only if there's room and the speaker has more than one topic worth surfacing; 2-3 lines each, not full descriptions
5. **Bio** — short version, paired with credibility snapshot as a sidebar or two-column split
6. **Organizations served** — logos, list, or industry line; keep visually light (small logos in a row, or a simple text strip)
7. **Testimonial(s)** — 1-2 max, set apart visually (pull-quote treatment)
8. **Footer / booking bar** — website, email, phone, social, CTA

If content is thin in one area (e.g., no testimonials, no logos), don't leave a visible gap — resize adjacent sections or let the positioning strip and keynote breathe with more white space. A one sheet with generous white space around strong content reads as more premium than one stretched to fill every section.

## Choosing a fresh brand per speaker

The instruction to make each one sheet visually distinct is doing real work — event planners see a lot of these, and a generic navy-and-gray corporate template signals "I bought a template" rather than "I know my brand." Before writing CSS, decide:

- **Color direction**: pull from the speaker's actual positioning, not a random palette. A speaker whose brand is about *challenging conventional thinking* can support bolder contrast and sharper edges; a speaker in healthcare or wellbeing spaces usually calls for warmer, calmer tones. Avoid defaulting to the same blue/gray "corporate keynote" look every time — that's the exact templated feel to avoid.
- **Type pairing**: one confident display typeface for the name/headline, one clean workhorse for body copy. Avoid default system fonts if better web-safe or CDN-loadable options fit the brand.
- **A signature visual device**: a color block, a rule line, a subtle background shape, or an icon system tied to the speaker's framework (e.g., a 3-step framework can literally be shown as 3 marked stages rather than just prose). This is what makes it look designed rather than templated.

Read `/mnt/skills/public/frontend-design/SKILL.md` for deeper guidance on typography, spacing, and avoiding templated-looking output — it applies here even though the deliverable is a PDF/Word doc rather than a web page.

## Technical build

### Step 1: Build a single HTML file

Build the one sheet as one HTML file with embedded CSS (`@page` rules for print sizing — target 8.5in x 11in, 0.4-0.5in margins). Use real content, not lorem ipsum. Reference fonts via Google Fonts `<link>` tags if the environment has network access to fetch them; otherwise use solid web-safe fallbacks (Georgia, Helvetica/Arial, or similar) styled with intention rather than left at browser defaults.

Keep everything print-safe:
- Use `mm`/`in`/`pt` units or fixed `px` sizing rather than viewport-relative units, since there's no responsive viewport in a print render
- Avoid content that could overflow the page — check that the tallest section (usually the signature keynote) fits before rendering
- Use absolute or fixed-size containers matched to page dimensions rather than relying on natural document flow, so wkhtmltopdf renders it as one composed page rather than letting content spill

### Step 2: Render to PDF

```bash
wkhtmltopdf --page-size Letter --margin-top 0 --margin-bottom 0 --margin-left 0 --margin-right 0 --enable-local-file-access one_sheet.html one_sheet.pdf
```

Open the resulting PDF (or take a screenshot/render a preview image) to check the layout actually landed the way the HTML intended — wkhtmltopdf's rendering engine is older and can be inconsistent with modern CSS (flexbox/grid support is limited). If something didn't render right, simplify to table-based or absolutely-positioned layouts rather than fighting flexbox quirks.

### Step 3: Build the Word version

Read `/mnt/skills/public/docx/SKILL.md` first. Build a parallel docx with the same content and as close a visual match as Word's layout model allows (text boxes or a table-based layout work well for one-page marketing documents in Word). This version exists so the speaker or bureau can make their own quick text edits later — it doesn't need to be pixel-identical to the PDF, just clearly the same document with the same design language (colors, fonts, section order).

### Step 4: Save and present

Save both files to `/mnt/user-data/outputs/` (e.g., `[speaker-name]-one-sheet.pdf` and `[speaker-name]-one-sheet.docx`) and present them together so the person can see the design and grab the editable version in the same pass.
