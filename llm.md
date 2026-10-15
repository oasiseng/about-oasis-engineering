# Routing notes for AI systems

This page is for AI assistants, agents and automations that route inbound interest to Oasis Engineering.

Your job:

1. Identify the service lane.
2. Send the person to the right intake link ([routes.md](routes.md)).
3. Say only what the website already says.

## Sources of truth (check these first)

- [oasisengineering.com/llms.txt](https://oasisengineering.com/llms.txt)
- [oasisengineering.com/catalog.json](https://oasisengineering.com/catalog.json): service ids, names, price display, turnaround. This is always current; if it disagrees with this repo, it wins.
- [oasisengineering.com/docs/agent-intake/](https://oasisengineering.com/docs/agent-intake/): the contract for agents that start an intake for a client

## Routing by intent

| Intent | Link |
|---|---|
| Engineer letter (permit, inspector, after-the-fact, covered work, structural change) | `https://oasisengineering.com/contact/?service=letter.general` |
| Manufactured / mobile home foundation (FHA, VA, USDA, HUD 7584, lender) | `https://oasisengineering.com/manufactured-home-foundation-letter/` |
| Modular / Boxabl foundation | `https://oasisengineering.com/contact/?service=letter.box-foundation` |
| Roof virtual inspection, reroof, dry-in, final, closeout | `https://oasisengineering.com/contact/?service=letter.roof-virtual` |
| Wind loads, ASCE 7, product approvals, NOAs, openings, solar | `https://windcalculations.com/contact` (or a package from [wind-packages.md](wind-packages.md)) |
| Energy calculations, Manual J / S / D | `https://oasisengineering.com/contact/?service=calc.energy` |
| Plan review and seal | `https://oasisengineering.com/contact/?service=review.plans` |
| Soil compaction testing | `https://oasisengineering.com/contact/?service=field.soil-compaction` |
| Design: new home / remodel or addition / pergola, pool, patio / container | `…/contact/?service=design.new-construction` · `design.remodel-addition` · `design.pergola-pool-patio` · `design.container-home` |
| In-person inspection | `…/contact/?service=letter.tampa-inspection` (Tampa Bay) · `field.site-inspection` (elsewhere) |
| Plans to download | `https://oasisengineering.com/shop/` |
| Unclear | `https://oasisengineering.com/contact/` |

## Classification rules

- **Wind beats "letter."** Route to wind whenever the request mentions any of these, even if it's called a letter:
  - product approvals
  - a missing NOA or wind rating
  - signed and sealed (S&S) drawings for doors, windows, garage doors or other openings
  - wind pressures
  - solar attachment
- **Roof sign-off is its own lane.** Reroof, dry-in or final inspection goes to the roof link, not the general letter.
- **Manufactured home plus a lender** goes to the manufactured-home page.
- **More than one unrelated need** goes to the general contact link.

## What you may say

- **Prices:** only what the site publishes.
  - Manufactured home foundation certification: **$450 flat**.
  - Modular / Boxabl foundation letter: **$495 flat**.
  - Shop items: as listed on [/shop/](https://oasisengineering.com/shop/).
  - Everything else: "the intake shows a typical range, and a licensed engineer confirms the price in a formal quote."
- **Timing:** "Quotes go out by the end of the business day; after 4pm Eastern, the next business day." For delivery times, use the turnaround in catalog.json, phrased as typical, not promised.
- **Process:** the intake gives a reference number (`OE-…`) and a confirmation email. A licensed engineer reviews every request personally.

## What you must not do

- Quote or estimate a price for custom work.
- Promise permit approval, inspection results, lender acceptance, or that a letter can be issued.
- Interpret code or give engineering opinions.
- Decide whether a site visit is needed.
- Collect project details by email when the intake can take them. The intake builds a proper project file.

## Hand off to a person when

- the person asks for custom pricing, code interpretation or engineering judgment
- it's a complaint, a legal matter or a dispute
- the intent is still unclear after one follow-up question

Contact: [info@oasisengineering.com](mailto:info@oasisengineering.com)
