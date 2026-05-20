---
title: "Consolidated investor report — design spec"
date: 2026-05-20
status: Approved structure, ready to draft
---

# Consolidated investor report — design spec

## Purpose

Produce a single investor / strategic-partner facing report that consolidates
the existing Span/XFRA research, competitive analysis, NW Ohio per-node
economics, presentation deck, and concept-doc work into one flowing prose
document. The output is one markdown file plus a generated PDF.

## Audience

Investor or strategic partner evaluating either (a) Span/XFRA as an
investment thesis or (b) the Northwest Ohio region as a place to site a
distributed-compute play. Assumes financial literacy and basic familiarity
with data-center vocabulary; does not assume prior knowledge of Span.

## Source materials (consolidated)

- `xfra-analysis-report.md` — strict analytical report (technical / business /
  strategic / risk / adjacency)
- `span-xfra-research-brief.md` — system primer (hardware, power, deployment,
  economics)
- `span-xfra-competitive-landscape.md` — six-category competitive map
- `nw-ohio-revenue-analysis.md` — NW Ohio per-node P&L and investor framing
- `concept-doc.md` — four directional-bet archetypes
- `index.html` / `span-xfra-presentation.pdf` — 17-slide presentation; used
  as framing/structure reference

## Output

- **Markdown file:** `span-xfra-investor-report.md` at repo root
- **PDF:** `span-xfra-investor-report.pdf` at repo root, generated via pandoc
  (with a LaTeX-engine fallback chain) or, if pandoc is unavailable, a
  Chrome/headless-browser conversion path.
- **Target length:** 16–18 pages of prose, plus tables. Roughly 8,000–11,000
  words.

## Structure (approved)

1. **Executive summary** (~1 page). Three paragraphs:
   - What XFRA is in one sentence; the headline thesis (residential headroom
     → saleable AI inference) and what's load-bearing.
   - Why it's investable — the political tailwind, the hardware credibility,
     and the three binary risks.
   - Why Northwest Ohio specifically: Meta is already here, AEP tariff
     arbitrage, and structurally the highest-margin geography in the model.

2. **The Northwest Ohio opportunity** (~2 pages). Lead with the regional hook.
   - Meta Bowling Green (350 MW, Wood County, online 2027) and the three
     other live prospects (Oregon OH, Waterville Twp, Lucas County).
   - AEP Ohio data-center tariff: >25 MW threshold, 85% take-or-pay,
     12-year term — and why distributed compute at 19 kW per node sits
     three orders of magnitude below it.
   - Residential power cost (~9.94¢/kWh AEP, ~9.5–9.8¢ Toledo Edison) vs.
     NV/AZ benchmark.
   - Per-node P&L table: NW Ohio vs. NV/AZ vs. CA.
   - Base-case revenue ($210K/node), $128K gross margin/node, 1,000-node
     pilot economics.

3. **What XFRA is** (~2 pages). The system primer.
   - Company, founders, funding, Pulte / Nvidia / Dell partnerships.
   - Per-node bill of materials and form factor (HVAC-sized outdoor pod).
   - Power envelope (~80 A / 19.2 kW, 200 A residential service compatible).
   - Homeowner economics (~$150/month covering electric + internet; in some
     markets both go to zero).
   - Pilot scope (100 homes, Q3 2026, Southwest, Pulte) and stated long-term
     goals (>1 GW/yr capacity 2027, 80,000 nodes).

4. **Technical viability** (~2 pages).
   - Hardware: low risk; conventional Dell + Nvidia + AMD integration.
   - Power envelope: low risk for new construction, high risk for retrofit.
   - Cooling and acoustic: standard tech; unverified maintenance/insurance.
   - Networking: 1 Gbps uplink is fine for inference, not for training.
   - Orchestration: most novel piece, least publicly documented; assertion,
     not evidence.
   - Summary risk table.

5. **Business viability & unit economics** (~2 pages).
   - The four-variable model (R – C_pwr – C_net – C_op).
   - Three independent back-solves converging on $180–230K/node revenue
     (retail GPU-hour discount, Congruent Ventures asset-value, Span's own
     $3M/MW framing).
   - Sensitivities (GPU resale compression, high-rate states, hyperscaler
     reluctance, channel slowdown).
   - Where the economics work (Southwest, NW Ohio) and where they don't
     (California without tariff innovation).

6. **Competitive landscape** (~2 pages).
   - Six categories: direct peers (Heata/Qarnot/Deep Green), modular prefab
     (Schneider/Vertiv/Crusoe Spark/Duos), edge colocation
     (EdgeConneX/EdgePresence), hyperscaler & telco edge (AWS Outposts,
     Azure Stack, GDC Edge, Verizon/AT&T), behind-the-meter generation
     (Crusoe/Bloom/FluxCore), grid-flex (Emerald + Nvidia, Verrus),
     decentralized GPU networks (io.net, Akash, Render).
   - Where Span wins (speed, latency proximity, capex/MW, political story).
   - Where Span loses or is at parity (cluster topology, cost per GPU-hour,
     service economics, security trust, capacity ceiling).
   - Most direct structural threats, ranked.

7. **Strategic positioning & risk inventory** (~2 pages).
   - Moat: panel installed base + builder channel + power-control IP. None
     alone is a moat; the combination is hard to copy in 3–4 years.
   - Risk tables: technical, operational, market/business, regulatory/
     political, catastrophic.
   - The two binary risks: (a) PUC tariff outcomes, (b) truck-roll cost
     scaling.

8. **Adjacent opportunities and four directional bets** (~2 pages).
   - Span's nearest adjacencies it isn't pursuing: utility grid-services,
     heat reuse, sovereign/institutional, insurance product, multi-rack
     site upgrade, Northeast with heat reuse, federal / DOD.
   - The four "what if it isn't Span" archetypes from concept-doc:
     **Hearth** (heat reuse, US Northeast), **Steeple** (cell towers /
     telco huts), **Civic** (municipal sovereign inference),
     **Confluence** (co-deployed with solar + storage).
   - Trade-off comparison: each beats Span on something, loses on something
     else.

9. **Watchlist & decision gates** (~1 page).
   - The eight things from `xfra-analysis-report.md` §8 that, if answered,
     change the assessment.
   - The five things from `nw-ohio-revenue-analysis.md` "what I'd want
     before writing a check."
   - Two new explicit decision gates for an investor: (a) first
     hyperscaler-tier anchor LOI, (b) first PUC ruling on residential
     aggregation.

10. **Sources** — full citation list grouped by topic, lifted from the source
    docs and deduplicated.

## Style

- Investor-grade prose. Sentences carry analytical weight; no filler.
- Preserve the evidence-rating convention from the source: **[S]** sourced
  from Span, **[T]** third-party with attribution, **[D]** derived in the
  report, **[I]** inferred.
- Tables preserved verbatim where they carry analytical weight (per-node
  P&L, risk matrices, competitive side-by-side). Don't paraphrase a table
  into prose.
- Headers numbered. Inline links to primary sources.
- No emojis. No introductory throat-clearing per section.

## Build / generation

- **Markdown:** written by Claude in one pass against this spec, then
  reviewed for placeholders, contradictions, and scope drift.
- **PDF generation strategy:**
  1. Prefer `pandoc` with a LaTeX engine (`xelatex` or `pdflatex`).
  2. If LaTeX is unavailable, fall back to `pandoc --pdf-engine=weasyprint`
     or `wkhtmltopdf`.
  3. If neither is installed, convert via Chrome headless against an HTML
     intermediate (`pandoc -t html5 → google-chrome --print-to-pdf`).
  4. If all fail, report the markdown is complete and stop short of PDF
     generation rather than ship a broken artifact.

## Out of scope

- New primary research. The report consolidates what's already in the repo;
  it does not add new sources or new claims.
- Republishing the interactive deck (`index.html`) as a separate artifact.
  The PDF of the deck is the deck artifact.
- A separate executive-only one-pager. Section 1 (Executive Summary) serves
  that purpose; if a standalone is wanted later, derive it then.

## Verification before completion

- The markdown renders cleanly on GitHub (tables, headers, links).
- The PDF generates without truncation; spot-check page count is in the
  16–18 page range.
- All citation links in the report are present in the consolidated Sources
  section (no orphan claims).
