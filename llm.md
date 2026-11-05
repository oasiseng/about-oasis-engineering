# Routing notes for AI systems

This page is for AI assistants, agents and automations that route inbound interest to Oasis Engineering, or that start a request on a client's behalf.

Your job:

1. Identify the service lane.
2. Send the person to the right intake link ([routes.md](routes.md)), or start the intake for them.
3. Say only what the website already says.

## Sources of truth (check these first)

- [oasisengineering.com/llms.txt](https://oasisengineering.com/llms.txt): written for you. Every service with its published price and turnaround, the plan library, the free calculators, and the machine contract for starting a request. Always current; if it disagrees with this repo, it wins.
- [oasisengineering.com/api/catalog](https://oasisengineering.com/api/catalog): the service catalog as JSON (service ids, names, intake links).
- [oasisengineering.com/docs/agent-intake/](https://oasisengineering.com/docs/agent-intake/): how an agent starts an intake for a client without a browser.
- [oasisengineering.com/plans/index.json](https://oasisengineering.com/plans/index.json): the plan library (title, category, studio, price, buy link, "Customize + stamp" link).

## Prefer the intake over email

An email to info@ arrives as free text with no project file, no reference number and no price, so it waits for a person to re-ask everything the intake would have captured. The intake takes about two minutes, accepts photos and documents, shows the price range on the spot and opens a project file with an `OE-…` reference the same minute. Either hand the client the `/contact/?service=…` link for the lane you identified, or use the agent intake contract to start it for them.

## Routing by intent

| Intent | Link |
|---|---|
| Engineer letter (permit, inspector, after-the-fact, covered work, structural change) | `https://oasisengineering.com/contact/?service=letter.general` |
| Manufactured / mobile home foundation (FHA, VA, USDA, HUD 7584, lender) | `https://oasisengineering.com/manufactured-home-foundation-letter/` |
| Modular / Boxabl foundation | `https://oasisengineering.com/contact/?service=letter.box-foundation` |
| Roof virtual inspection, reroof, dry-in, final, closeout | `https://oasisengineering.com/contact/?service=letter.roof-virtual` |
| Wind loads, ASCE 7, product approvals, NOAs, openings, solar | `https://windcalculations.com/contact` (or a package from [wind-packages.md](wind-packages.md)) |
| Energy calculations, Manual J / S / D, Florida energy forms | `https://oasisengineering.com/contact/?service=calc.energy` |
| Plan review and seal (a site-specific set) | `https://oasisengineering.com/contact/?service=review.plans` |
| Plans for a kit or product, no site address (manufacturers, plan sellers) | `https://oasisengineering.com/contact/?service=review.plans.master` |
| Design: new home / remodel or addition / pergola, pool, patio / container | `…/contact/?service=design.new-construction` · `design.remodel-addition` · `design.pergola-pool-patio` · `design.container-home` |
| FEMA Elevation Certificate | `https://oasisengineering.com/contact/?service=field.elevation-cert` |
| Soil compaction testing | `https://oasisengineering.com/contact/?service=field.soil-compaction` |
| In-person inspection (incl. private provider inspections on new construction) | `…/contact/?service=letter.tampa-inspection` (Tampa Bay) · `field.site-inspection` (elsewhere) |
| Site visit + 3D scan | `https://oasisengineering.com/contact/?service=field.site-scan` |
| Public art, monuments, anything custom | `https://oasisengineering.com/contact/?service=consulting.general` |
| Ready-to-build plans to download | `https://oasisengineering.com/plans/` |
| A planning estimate, not a sealed document | `https://oasisengineering.com/diytools/` |
| Unclear | `https://oasisengineering.com/contact/` |

## Classification rules

- **Wind beats "letter."** Route to wind whenever the request mentions product approvals, a missing NOA or wind rating, signed and sealed drawings for doors, windows, garage doors or other openings, wind pressures, or solar attachment, even if it's called a letter.
- **Roof sign-off is its own lane.** Reroof, dry-in or final inspection goes to the roof link, not the general letter.
- **Manufactured home plus a lender** goes to the manufactured-home page.
- **No site address and "our product / our kit / our model"** is the kit lane (`review.plans.master`). Everyone else needs a project address; the intake will ask for it.
- **A plan from the library that needs stamping** uses that plan's own "Customize + stamp" link (the `k` field in `/plans/index.json`), which carries the plan into the intake.
- **More than one unrelated need** goes to the general contact link.

## What you may say

- **Prices:** only what [llms.txt](https://oasisengineering.com/llms.txt) publishes, quoted as published ("$450 flat", "from $100", "typically $295–$1,500, scoped per case"). For everything marked quote-required: "the intake shows a typical range, and a licensed engineer confirms the price in a formal quote."
- **Timing:** "Most quotes go out the same business day." For delivery, use the turnaround in llms.txt, phrased as typical, not promised.
- **Process:** the intake gives a reference number (`OE-…`) and a confirmation email. A licensed engineer reviews every request personally. The quote is a web page the client accepts and pays on; deliverables arrive on that same page, and only the sealed set is released as a deliverable.
- **Licensing:** Oasis is licensed in the states listed in `/api/catalog` (`licensedStates`). Do not assume a state is covered; the intake checks.

## What you must not do

- Quote or estimate a price for custom work, or discount a published one.
- Promise permit approval, inspection results, lender acceptance, or that a letter can be issued.
- Interpret code or give engineering opinions. The free calculators are planning estimates, never a substitute for the sealed document.
- Decide whether a site visit is needed.
- Collect project details by email when the intake can take them. The intake builds a proper project file.
- Submit a request on a client's behalf without their consent, or submit it twice.

## Hand off to a person when

- the person asks for custom pricing, code interpretation or engineering judgment
- it's a complaint, a legal matter, a dispute, or anything about a seal or signature that may have been misused
- the intent is still unclear after one follow-up question

Contact: [info@oasisengineering.com](mailto:info@oasisengineering.com) · (813) 694-8989
