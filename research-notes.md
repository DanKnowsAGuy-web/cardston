# Cardston proposal page: research notes (September 2026)

## v2: full redesign (this version)

Dan asked for a full rebuild after reviewing v1: too convoluted, mixed fonts, clipped text,
and the Big Rock re-theme was too heavy-handed. This version:

- Rebuilt `index.html` from a clean slate with its own stylesheet, `assets/style.css`. It does
  not reuse any component, class, or CSS custom property from the old `assets/site.css`
  (which has been removed from the repo, along with the old self-hosted `assets/fonts/`
  folder, both now unused).
- One typeface throughout: Inter (Google Fonts), falling back to the `-apple-system` stack.
- One accent color: Big Rock navy `#26306C`, used only for the button, the big stat number,
  and the cash-flow chart. The coral `#EC5D3C` from Big Rock's site is not used anywhere in
  this version, per instruction to keep it to at most a light touch.
- Branding is light touch: the Big Rock Power PNG (which has its own opaque white background)
  sits directly in a plain white header, unchanged, no chip or badge needed since the header
  is now white instead of navy. "In partnership with Energy+" sits top right in small type.
- Language rule: the words "waste," "wasting," "upgrade," and "efficiency" do not appear
  anywhere in the page's visible copy (grepped and confirmed; the one hit for "efficiency" is
  inside an unmodifiable NRCan URL path, not visible text). "Energy overspend" is used
  throughout instead.
- Copy was cut hard: every section is a short head plus one or two lines, the funding section
  is a plain two-column list instead of a table, and the "who's involved" section from v1 was
  folded into the header/footer credit line instead of a standalone section.

### The Energy+ logo on a white header

`assets/img/energy-plus-logo.png` is white/near-white artwork on a transparent background
(confirmed by canvas-sampling the PNG: dominant non-transparent pixel value is ~(255,255,255)
everywhere ink appears). No separate dark version of this logo exists anywhere in the other
DanKnowsAGuy-web repos checked (cpl, cryogenex-academy, redstone-landrys all ship the exact
same file, byte for byte). On the new white header, `filter: invert(1)` is applied to it,
which turns the white artwork solid dark/near-black. Verified visually in the browser: the
wordmark renders as a crisp dark "ENERGY+" mark, fully legible against white.

### The one number council cares about: the property tax levy

For a town, the property tax levy is the annual number council answers to, the same way NOI
matters for multifamily or covers matter for restaurants. Cardston's own audited financial
statements give this directly:

- **Net municipal property taxes, 2024 actual: $3,170,684** (2024 budget: $3,182,086; 2023
  actual: $2,946,554). Source: *Town of Cardston Consolidated Financial Statements, Year
  Ended December 31, 2024*, Schedule of Property and Other Taxes (Schedule 3), page 10:
  https://www.cardston.ca/public/download/files/263280
  (This is "net municipal property taxes" after backing out the Alberta School Foundation
  Fund requisition, the designated industrial property requisition, and other pass-through
  requisitions, i.e. the actual town-controlled tax levy, not the total collected including
  provincial education tax.)
- **Occupied private dwellings (households), 2021 Census: 1,261.** Source: Statistics Canada,
  2021 Census of Population, Cardston, Town (T), Alberta:
  https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/details/page.cfm?Lang=E&SearchText=Cardston&DGUIDlist=2021A00054803004&GENDERlist=1,2,3&STATISTIClist=1&HEADERlist=0

**The math** (illustrative annual savings figure of $35,000/year carried over from the v1
draft, built from published benchmark ranges for arena/pool/town-office/water-wastewater
retrofits, not from Cardston's own bills, which we have not seen):

- $35,000 / $3,170,684 = 0.011039... = **1.10%**, rounded to **1.1%** in the headline stat.
  This is the "same as a 1.1% property tax increase Cardston doesn't have to pass" framing.
- $35,000 / 1,261 households = $27.76/household/year, rounded to **about $28 a year per
  household** for the secondary equivalent.

Both figures are labeled illustrative on the page and tied to the same $35,000/year
illustrative savings estimate used throughout the rest of the page (the cash-flow chart, the
three-streams framing). If Cardston's real interval data produces a different savings number,
both the percentage and the per-household figure need to be recalculated the same way:
divide the real annual savings by $3,170,684 for the tax-equivalent percentage, and by 1,261
for the per-household figure.

I was able to find the actual levy (not just the household count), so both figures are shown
together as requested; nothing here relies on the fallback of household-only reporting.

## Brand used: Big Rock Power (unchanged from v1)

- Searched for **Manitou Energy** (the venture reportedly formed by Larry Peters, Brian at
  brian@wickhorst.com, and Ben at sunbanksolar.ca) via web search for a site, logo, or brand
  presence. No findable website, social profile, or press exists under that name as of
  September 2026. Search results only surfaced unrelated companies ("Manitok Energy," the
  French "Manitou Group" heavy-equipment maker, and "Manitou, Manitoba").
- Per the fallback instruction, used **Big Rock Power** (bigrockpower.ca), Larry Peters'
  company, instead. Confirmed real: Larry Peters authors the company blog and is reachable at
  larry.peters@bigrockpower.ca. Site: https://www.bigrockpower.ca/
- Logo source: https://static.wixstatic.com/media/09c530_9961d95fb40e47619df4529863160dc7~mv2.png
  ("Big Rock White Background.png"), saved as `assets/img/bigrockpower-logo.png` (1505x563
  PNG, opaque white background, navy and gold wordmark). This version places it as-is in a
  plain white header rather than re-theming the whole page around it.
- Big Rock's own brand colors, for reference (sampled directly from the live site): navy
  `#26306C`, coral `#EC5D3C`, yellow `#FED214`. Only the navy is used in this redesign.

## Funding & financing programs checked (status as of September 2026, unchanged from v1)

| Program | Level | Status | Detail |
|---|---|---|---|
| FCM Green Municipal Fund, Community Buildings Retrofit initiative | Federal (delivered by FCM) | **Open** | Rolling/year-round intake until funds allocated. All Canadian municipalities eligible except a short excluded list (Low Carbon Cities Canada namesake municipalities). Source: https://greenmunicipalfund.ca/community-buildings-retrofit-initiative |
| NRCan / Housing, Infrastructure and Communities Canada, Green and Inclusive Community Buildings (GICB) | Federal | **Closed** | Current application intake is closed; results being communicated to applicants. Program itself runs to March 2029 (Budget 2024 top-up), so a future intake is possible. Source: https://housing-infrastructure.canada.ca/gicb-bcvi/index-eng.html |
| Canada Infrastructure Bank, Building Retrofits Initiative | Federal | **Open, via financing partners** | CIB doesn't lend directly to a single small town; it partners with lenders (e.g., a $100M facility with Scotiabank, $50M with Efficiency Capital) who then finance retrofits. Best fit for a larger, pooled, or portfolio-scale project rather than a standalone small-town application. Source: https://cib-bic.ca/en/building-retrofits-initiative/ |
| Canada Community-Building Fund (rebranded in 2026 as the Building Communities Strong Fund, Community Stream) | Federal, flows through Alberta | **The town's own money** | This is a formula-based allocation Cardston already receives annually (successor to the old federal Gas Tax Fund). Not a competitive grant we apply for; council can choose to direct part of its own existing allocation to eligible capital categories within program rules. Source: https://www.alberta.ca/canada-community-building-fund |
| Alberta Local Government Fiscal Framework (LGFF) | Alberta | **The town's own money** | Same pattern: formula-based capital funding Alberta municipalities already receive. Not confirmed whether energy retrofits are specifically named as an eligible category; council can direct funds within program rules. Source: https://www.alberta.ca/local-government-fiscal-framework-capital-funding |
| Municipal Climate Change Action Centre (MCCAC) | Alberta | **Winding down** | Alberta Municipalities announced in July 2026 that MCCAC is winding down province-wide (target completion by June 2027). Some 2026 deadlines were extended and existing signed agreements proceed, but this is not a reliable ongoing source going forward. Source: https://mccac.ca/2026/07/17/the-mccac-is-winding-down-after-17-successful-years/ |
| Emissions Reduction Alberta (ERA) | Alberta | **Not a fit today** | Current calls focus on industrial transformation and technology innovation, not small-municipality building work. No dedicated municipal buildings program found. Source: https://www.eralberta.ca/apply-for-funding/ |
| Cardston's own municipal electric utility | Local | **To confirm directly** | Cardston owns and operates its own electrical distribution system rather than being served by FortisAlberta. No specific program for the town's own facilities found in public search. |

### Tax credits: correctly scoped

Towns do not pay income tax, so federal tax credits (e.g. the Clean Technology Investment Tax
Credit) do not apply to Cardston directly. A credit could only apply to a private financing
partner inside the deal structure, showing up as better pricing to the town, never as a
credit the town claims itself. Stated this way on the page, not overstated.

### Financing options (no debt-treatment claims)

- **Savings-funded financing**: paid down from the savings the project creates; the page says
  the structure and its treatment on Cardston's books are confirmed with the town's own
  finance team before signing.
- **Cash**: offered as a straightforward alternative.

## What's unverified / illustrative

- The $35,000/year illustrative savings figure, the 1.1% stat, the $28/household figure, and
  the cash-flow chart are all modeled examples, not a reading of Cardston's real bills, which
  we have not seen. Labeled illustrative in three places on the page.
- Whether Alberta's LGFF and the Community-Building Fund specifically list energy work as an
  eligible category (versus general infrastructure) wasn't confirmed in public guidelines;
  the page describes them as "the town's own money, which council can choose to direct here,"
  not a guaranteed fit.
- No Cardston utility-side program was found; the page says we'll check directly.

## Diagnostician section

Reused the "Cliff Suljak, Chief Technical Engineer" content and photo (`cliff-lab.jpg`) from
the `redstone-landrys` and `cryogenex-academy` DanKnowsAGuy-web repos. No credentials beyond
what those pages already state were added. One phrase was reworded to avoid the banned word
"efficiency": "a $600 million utility efficiency program" became "a $600 million utility
program" without changing the underlying claim.

## Style compliance

- Zero em dashes and en dashes in visible text (grepped and confirmed clean).
- Body text is 18px (1.125rem) base, larger for ledes and card copy; near-black ink on white
  or light grey, high contrast throughout.
- Headlines use `text-wrap: balance` plus manual verification: every h1/h2/h3 was checked at
  375px, 768px, and 1280px with a script that wraps each word in a span and confirms the last
  line never holds exactly one word. One real issue was caught and fixed this way: the
  "Energy overspend" card title broke to two words-on-two-lines at 768px under the old
  3-column breakpoint; the breakpoint was moved from 700px to 860px so the 3-column grid only
  engages where there's room.
- No `scrollWidth > clientWidth` overflow anywhere on the page at 375, 768, or 1280px
  (checked programmatically across every element, not just visually).
- No partner commission percentages appear anywhere on the page.
- `robots.txt` and the `noindex, nofollow` meta tag are unchanged.
