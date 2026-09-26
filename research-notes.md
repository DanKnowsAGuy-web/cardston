# Cardston proposal page: research notes (September 2026 rework)

## Brand used: Big Rock Power

- Searched for **Manitou Energy** (the venture reportedly formed by Larry Peters, Brian at
  brian@wickhorst.com, and Ben at sunbanksolar.ca) via web search for a site, logo, or brand
  presence. No findable website, social profile, or press exists under that name as of
  September 2026. Search results only surfaced unrelated companies ("Manitok Energy",
  the French "Manitou Group" heavy-equipment maker, and "Manitou, Manitoba").
- Per the fallback instruction, used **Big Rock Power** (bigrockpower.ca), Larry Peters'
  company, instead. Confirmed real: Larry Peters authors the company blog and is reachable
  at larry.peters@bigrockpower.ca. Site: https://www.bigrockpower.ca/
- Logo source: https://static.wixstatic.com/media/09c530_9961d95fb40e47619df4529863160dc7~mv2.png
  ("Big Rock White Background.png"), downloaded into `assets/img/bigrockpower-logo.png`
  (1505x563 PNG, white background, navy wordmark).
- Brand colors sampled directly from the live site (canvas pixel sampling of the logo, plus
  computed styles of on-page buttons/links):
  - Navy (primary / wordmark / dark backgrounds): `#26306C` (sampled as rgb(38,48,108))
  - Coral orange (accent / links / highlighted numbers): `#EC5D3C`
  - Yellow (secondary gradient stop on CTA buttons): `#FED214`
- Applied navy as the page's `--graphite` token and coral orange as `--amber`, per the
  site.css "RE-SKIN CONTRACT" (override only the CSS custom properties in `:root`; layout,
  motion, and disclosure wiring are untouched). See the `:root` override block at the top
  of `index.html`'s `<style>`.
- Energy Plus is credited as "In partnership with Energy+" in the header, right side, using
  the existing `assets/img/energy-plus-logo.png` at reduced size/opacity next to the Big
  Rock Power logo.

## Funding & financing programs checked (status as of September 2026)

| Program | Level | Status | Detail |
|---|---|---|---|
| FCM Green Municipal Fund, Community Buildings Retrofit initiative | Federal (delivered by FCM) | **Open** | Rolling/year-round intake until funds allocated. All Canadian municipalities eligible except a short excluded list (Low Carbon Cities Canada namesake municipalities). Source: https://greenmunicipalfund.ca/community-buildings-retrofit-initiative |
| NRCan / Housing, Infrastructure and Communities Canada, Green and Inclusive Community Buildings (GICB) | Federal | **Closed** | Current application intake is closed; results being communicated to applicants. Program itself runs to March 2029 (Budget 2024 top-up), so a future intake is possible. Source: https://housing-infrastructure.canada.ca/gicb-bcvi/index-eng.html |
| Canada Infrastructure Bank, Building Retrofits Initiative | Federal | **Open, via financing partners** | CIB doesn't lend directly to a single small town; it partners with lenders (e.g., a $100M facility with Scotiabank, $50M with Efficiency Capital) who then finance retrofits. Best fit for a larger, pooled, or portfolio-scale project rather than a standalone small-town application. Source: https://cib-bic.ca/en/building-retrofits-initiative/ |
| Canada Community-Building Fund (rebranded in 2026 as the Building Communities Strong Fund, Community Stream) | Federal, flows through Alberta | **The town's own money** | This is a formula-based allocation Cardston already receives annually (successor to the old federal Gas Tax Fund). It is not a competitive grant we apply for on the town's behalf; council can choose to direct part of its own existing allocation to eligible capital categories (which can include recreation-facility infrastructure) within program rules. Source: https://www.alberta.ca/canada-community-building-fund |
| Alberta Local Government Fiscal Framework (LGFF) | Alberta | **The town's own money** | Same pattern as above: formula-based capital and operating funding Alberta municipalities already receive. Not confirmed whether energy retrofits are specifically named as an eligible category; council can direct funds to infrastructure priorities within program rules. Source: https://www.alberta.ca/local-government-fiscal-framework-capital-funding |
| Municipal Climate Change Action Centre (MCCAC) — Community Energy Conservation, Municipal Electricity Generation, etc. | Alberta | **Winding down** | Alberta Municipalities announced in July 2026 that MCCAC is winding down province-wide (target completion by June 2027), per provincial government direction. Some 2026 application deadlines were extended (to April 30, 2026) and existing signed agreements proceed, but this is not a reliable ongoing funding source going forward. Source: https://mccac.ca/2026/07/17/the-mccac-is-winding-down-after-17-successful-years/ |
| Emissions Reduction Alberta (ERA) | Alberta | **Not a fit today** | Current ERA funding calls focus on industrial transformation and technology innovation, not small-municipality building retrofits. No dedicated municipal buildings program found. Worth monitoring for new calls. Source: https://www.eralberta.ca/apply-for-funding/ |
| Cardston's own municipal electric utility | Local | **To confirm directly** | Cardston owns and operates its own electrical distribution system rather than being served by FortisAlberta (confirmed on the original page via cardston.ca). No specific conservation/incentive program for the town's own facilities was found in public search; we'll ask the utility directly once engaged. |

### Tax credits: correctly scoped

Towns do not pay income tax, so federal tax credits (e.g., the Clean Technology Investment
Tax Credit) do not apply to Cardston directly. The page notes that a credit could apply to
a private financing partner inside the deal structure, and would show up only as better
pricing to the town, never as a credit the town claims itself. This is stated correctly on
the page and is not overstated.

### Financing options presented (no debt-treatment claims)

- **Savings-funded financing**: paid down from the energy and maintenance savings the
  project creates. The page explicitly says the structure and its treatment on Cardston's
  books will be confirmed with the town's own finance team before signing. No "off balance
  sheet" or "no new debt" claim is made anywhere on the page.
- **Paying cash**: offered as a straightforward alternative if the town prefers it.

## What's unverified / illustrative

- All dollar figures in the "three streams" and "monthly cash flow" visuals are illustrative
  placeholders, explicitly labeled as such in the chart captions and fine print. They are
  not derived from Cardston's actual utility bills, which we have not seen.
  Real figures replace them once Cardston shares a year of interval data and recent bills.
- Whether the Alberta LGFF and Canada Community-Building Fund specifically list energy
  retrofits as an eligible capital category (versus general infrastructure) was not fully
  confirmed in public program guidelines during this research pass; the page describes them
  correctly as "the town's own funding, which council can choose to direct here" rather than
  claiming a guaranteed fit.
- No specific Cardston-utility-side conservation program was found; the page says we'll
  check with the utility directly.

## Diagnostician section

Reused the "Cliff Suljak, Chief Technical Engineer" section structure, copy, and photo
(`cliff-lab.jpg`) from the `redstone-landrys` and `cryogenex-academy` DanKnowsAGuy-web repos.
No credentials beyond what those pages already state were added (Sandia National
Laboratories sole-source contract; built the quality program for a $600 million utility
efficiency program).

## Style compliance

- Zero em dashes and en dashes in visible text (grepped and confirmed clean).
- Body copy uses `max(var(--step-1), 1.2rem)` (>= 19.2px) throughout, well above the 18px
  floor.
- Headlines rely on the site's existing global `text-wrap: balance` on h1/h2/h3.
- No partner commission percentages appear anywhere on the page.
- `robots.txt` and the `noindex, nofollow` meta tag are unchanged.
