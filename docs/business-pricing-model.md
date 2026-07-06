# Business & Pricing Model — Smart-Home & HEMS Consulting (Kleingewerbe)

**Catchment:** Olching + western Munich suburbs (Gröbenzell, Puchheim, Germering, Fürstenfeldbruck), Landkreis Fürstenfeldbruck (FFB)
**Business model:** Solo IT / System-Integration & Home-Energy-Management (HEMS) consultant — *not* an electrician
**Legal form:** Kleingewerbe · § 19 UStG Kleinunternehmerregelung · Dienstvertrag (§ 611 BGB)
**Document status:** Internal planning draft · Figures for 2026 Bavaria · `~` = approximate, all client/market counts are estimates
**Prepared:** 2026-07

---

## ⚠️ Assumptions Box (read first)

Every downstream number rests on these. Change these, change the model.

| # | Assumption | Value used | Confidence |
|---|------------|-----------|------------|
| A1 | Core catchment population (5 towns) | ~150,000 residents | Med |
| A2 | Persons per household (BY suburban) | ~2.2 | High |
| A3 | Core catchment households | ~68,000 | Med |
| A4 | Owner-occupied single-/two-family home share | ~40% of HH → ~27,000 | Med-Low |
| A5 | Affluent + tech-curious subset (can spend €1k+ discretionary on home tech) | ~25% → ~6,800 | Low |
| A6 | PV **or** heat-pump owner/planner subset (energy-motivated) | ~25% of A5 → ~1,700 | Low |
| A7 | Solo billable capacity (evenings/weekends) | ~10–12 h/week → **~500 h/yr** | Med |
| A8 | Target effective hourly value | **~€85–100/h** | Anchor |
| A9 | Blueprint effort | ~5 h | Med |
| A10 | HEMS (Tier 2) effort | ~18 h | Med |
| A11 | Full Retrofit (Tier 3) effort | ~50 h | Med |
| A12 | Realistic Year-1 conversion of engaged leads → clients | very low single-digit % of A6 | Low |
| A13 | § 19 UStG turnover ceiling (2026) | **€25,000 prior yr / €100,000 current yr** | High — see §7 |
| A14 | Hardware handled as near-cost pass-through + small handling margin | ~10–15% | Policy choice |

> **Threshold correction:** The €22,000 figure in the brief was the § 19 UStG prior-year limit **through 2024**. The 2025 reform (effective 01.01.2025) raised it to **€25,000 (Vorjahr) / €100,000 (laufendes Jahr)**. This document uses the current **€25,000** figure. See §7.

---

## 1. Executive Summary

The FFB district and Olching combine two rare traits: **above-average purchasing power (~120–130% of the national index)** and a **housing stock dominated by owner-occupied single-family homes** — exactly the substrate a wireless smart-home + energy retrofit needs. Homeowners here are being pushed by high energy prices, dynamic tariffs (Tibber/Awattar), PV and heat-pump adoption, and a severe electrician shortage (>96,500 vacant electrical roles nationally per ZVEH) — yet their only options today are a €8k–25k+ KNX/Loxone hardwired system from an overbooked Elektromeister, a €20k+ boutique integrator aimed at Neubau luxury, or cloud-locked MediaMarkt/MyHammer kit with no real automation logic. **The gap is affluent suburban *wireless retrofit* + *local-first HEMS*: Home Assistant, Shelly/Zigbee/Matter, dynamic-tariff and PV-surplus automation, delivered by a consultant who coordinates the client's own Elektrofachbetrieb for any 230V work.** A solo operator can serve this from home evenings and weekends with near-zero fixed costs and a recurring remote-care revenue tail — a low-risk, high-margin side business with a clear path to (and a deliberate decision point at) the § 19 UStG turnover ceiling.

---

## 2. Target Market Sizing (SOM Funnel)

The district has ~220,000 residents; this business does not realistically serve all of it. The **core catchment** is the tight cluster where drive time is short and word-of-mouth compounds: Olching (~30k), Gröbenzell, Puchheim, Germering, and Fürstenfeldbruck town — together **~150,000 residents**.

### Funnel (top-down, deliberately conservative)

| Stage | Filter | Households | Basis |
|-------|--------|-----------:|-------|
| 1 | Core catchment population | 150,000 residents | A1 |
| 2 | → Total households (÷ ~2.2) | **~68,000** | A2, A3 |
| 3 | → Owner-occupied 1-/2-family homes (~40%) | **~27,000** | A4 |
| 4 | → Affluent + tech-curious (~25%) | **~6,800** | A5 |
| 5 | → PV or heat-pump owner/planner (~25%) | **~1,700** | A6 |
| 6 | → Reachable/engaged leads per year (solo marketing reach, ~3%) | **~50** | judgment |
| 7 | → **Realistic paying clients / yr (capacity-capped)** | **~15–18** | §6, A7 |

**The binding constraint is capacity, not demand.** Even a pessimistic read of Stage 5 (~1,700 energy-motivated affluent SFH owners) dwarfs what one person can deliver in evenings and weekends. At ~500 billable hours/year (A7), the operator is capacity-limited to roughly **15–18 projects/year** across the tier mix (§6). The market is effectively unlimited relative to solo throughput — which means **pricing power sits with the operator**, and the strategy is to raise price/select clients, not chase volume.

**Serviceable Obtainable Market (SOM), Year 1:** ~15–18 projects + a growing recurring base. **This is <0.3% of the affluent SFH pool (Stage 4)** — a tiny, defensible sliver.

---

## 3. Customer Segments (Personas)

| Persona | Who | Trigger | Pain | Willingness to Pay | Best-fit tier |
|---------|-----|---------|------|--------------------|---------------|
| **"Frustrated Solar Owner" (Stefan, 52)** | Has PV (+ maybe battery/wallbox), engineer/manager mindset | Electricity bill + "my PV export earns cents, import costs a fortune" | Inverter app is a silo; no PV-surplus EV charging; no dynamic-tariff optimization | **High** — sees direct €-logic; €1,500–2,500 is "a few years of savings" | **Tier 2 (HEMS)** + Care |
| **"High-Income Commuter" (Familie Berger, 40s)** | Dual-income, SFH, munich-commute, time-poor, cash-rich | Renovation, new build-out, "want it to just work + look premium" | No time to DIY; wants concierge, not a hobby; hates vendor lock-in but fears KNX price/rigidity | **Very high** — €4k–6k acceptable if turnkey & tasteful | **Tier 3 (Full Retrofit)** + Care |
| **"AAL / Elderly-Family Retrofit" (adult child arranging for parents)** | Buyer ≠ occupant; safety & reassurance driven | Aging parent, fall/leak/heat worries, "keep them independent longer" | Wants remote visibility (leak, door, temperature, presence), simplicity for the parent | **High** — emotional + funded by adult child; recurring monitoring is the point | **Tier 2 (scaled to AAL)** + **premium Care** |
| **"Curious Tinkerer" (secondary)** | Already runs some HA, hit a wall | Stuck on an integration/automation | Wants expert unblocking, not a full build | Low-med — one-off | **Tier 1 (Blueprint)** |

**Note on WTP:** In this catchment, price is a *signal of competence*, not merely a cost. Under-pricing repels the Berger/Stefan segments (reads as "hobbyist"). See §8.

---

## 4. Service Packages & Pricing (Core Section)

**Pricing philosophy:** value-based flat fees, **not** hourly. Hardware is a transparent near-cost pass-through (A14) so the client trusts the advice is vendor-neutral; the operator earns on *integration expertise and time*, anchored to a **~€85–100/h effective value** (A8).

### Tier 1 — "Blueprint / Beratung" (consulting only)

**Flat fee: €450** (range €350–€500)

- **Included:** 1 on-site or video walkthrough; needs & goals assessment; documented system architecture (HA topology, device recommendations, Zigbee/Matter vs. Shelly choices, network/VLAN notes); a phased shopping/implementation roadmap the client can execute themselves *or* hand to any integrator; dynamic-tariff feasibility check.
- **Deliverable:** a written "Blueprint" PDF. No hardware, no install.
- **Strategic role:** low-risk entry, lead-magnet, and **credited toward Tier 2/3 if they upgrade within 90 days** (de-risks the buy).

| Line item | Hours | € |
|-----------|------:|---:|
| Consult + site assessment | 2.0 | — |
| Architecture + roadmap write-up | 2.5 | — |
| Admin/scheduling | 0.5 | — |
| **Total effort** | **5.0** | — |
| **Price** | | **€450** |
| Hardware pass-through | | €0 |
| **Effective hourly** | | **~€90/h** |

---

### Tier 2 — "Energy Core / HEMS" (the flagship)

**Service fee: €1,500** (range €1,200–€1,800) **+ hardware at pass-through**

- **Included:** pre-configured Home Assistant hub (HA Green / Yellow / mini-PC); dynamic-tariff integration (Tibber/Awattar); **PV-surplus logic** (surplus EV charging / heat-pump nudging where hardware allows); wallbox + heat-pump + inverter integration; core energy dashboard; up to ~2 "energy rooms" of sensing; handover + training session; **coordination brief for the client's Elektrofachbetrieb** if any 230V metering/CT install is needed (operator does *not* touch 230V).
- **Hardware (typical, pass-through):** hub ~€120–200, energy meter/CT clamp (e.g. Shelly Pro 3EM) ~€120, misc Shelly/Zigbee ~€100–250 → **~€350–650**, billed at cost + ~10–15% handling (A14).

| Line item | Hours | Notes |
|-----------|------:|-------|
| Discovery + design (or credited Blueprint) | 3.0 | |
| Hub provisioning & base config | 3.0 | |
| Tariff + PV/heat-pump/wallbox integration | 6.0 | the hard, high-value part |
| Dashboard + automations | 3.0 | |
| On-site handover + training | 2.0 | |
| Documentation | 1.0 | |
| **Total effort** | **~18.0** | |

| Economics | € |
|-----------|---:|
| Service fee | 1,500 |
| Hardware (pass-through, cost) | ~500 |
| Handling margin on hardware (~12%) | ~60 |
| **Client pays** | **~2,060** |
| Operator revenue (service + handling) | ~1,560 |
| **Effective hourly (service ÷ 18h)** | **~€83/h** |

> AAL variant: swap PV/tariff work for leak/door/temperature/presence sensing + remote-visibility dashboard; similar effort, pairs with **premium Care** retainer.

---

### Tier 3 — "Full Retrofit / Premium" (turnkey)

**Service fee: €4,800** (range €3,500–€6,000+) **+ hardware at pass-through**

- **Included:** whole-home wireless retrofit (multi-room lighting/blinds/climate/sensing via Shelly + Zigbee/Matter + Thread); full HEMS as Tier 2; multiple polished dashboards (wall tablet + mobile + optional voice); **active project management & scheduling of the client's Elektrofachbetrieb** (operator specs, electrician installs 230V modules, operator commissions); robust local network segmentation; 30-day post-launch tuning; 3 months of Care included.
- **Hardware (typical, pass-through):** ~€1,500–3,500 depending on room count and blind/relay density.

| Line item | Hours | Notes |
|-----------|------:|-------|
| Deep design + electrician spec | 6.0 | |
| Procurement + staging | 4.0 | |
| Multi-room commissioning (post-electrician) | 20.0 | |
| Dashboards + voice + scenes | 10.0 | |
| Handover, training, docs | 4.0 | |
| 30-day tuning | 6.0 | |
| **Total effort** | **~50.0** | |

| Economics | € |
|-----------|---:|
| Service fee | 4,800 |
| Hardware (pass-through, cost) | ~2,500 |
| Handling margin (~12%) | ~300 |
| **Client pays** | **~7,600** |
| Operator revenue (service + handling + 3mo Care) | ~5,190 |
| **Effective hourly (service ÷ 50h)** | **~€96/h** |

---

### Recurring — "Care / Remote Monitoring" retainer

**€29/month** typical (tiers €19 / €29 / €49)

| Plan | € / mo | Includes |
|------|-------:|----------|
| **Care Basic** | 19 | Uptime Kuma NOC monitoring, monthly health check, OS/HA update supervision, email support |
| **Care Plus** | 29 | + secure remote fixes via Tailscale, priority response, 1 remote session/mo, config backups |
| **Care AAL/Premium** | 49 | + proactive alert triage (leak/door/temp/offline), SLA-style response, quarterly on-site, family-facing status |

**Justification (why this is the real business):**
1. **Recurring, high-margin, near-zero marginal cost** — Tailscale + Uptime Kuma on a shared VPS costs ~€0.30/client/mo to run.
2. **Solves the #1 fear** ("what if it breaks and I can't fix it?") — the objection that otherwise kills the sale.
3. **Local-first HA needs a human** where cloud platforms auto-update; Care *is* the substitute for Nabu Casa/vendor cloud — and keeps data sovereignty.
4. **Compounding MRR** turns lumpy project income into predictable revenue; a base of 30 Care clients ≈ €900+/mo passive.
5. **Retention loop** — Care clients are the warm pipeline for upgrades and referrals.

---

### Tier comparison

| | Blueprint | Energy Core (HEMS) | Full Retrofit |
|---|---:|---:|---:|
| Service fee | €450 | €1,500 | €4,800 |
| Hardware (client, pass-through) | €0 | ~€560 | ~€2,800 |
| **Client total** | **€450** | **~€2,060** | **~€7,600** |
| Operator hours | 5 | 18 | 50 |
| Operator revenue | €450 | ~€1,560 | ~€5,190 |
| **Effective €/h** | **~€90** | **~€83** | **~€96** |
| Care attach | optional | strong | included 3mo |

---

## 5. Cost Structure & Unit Economics

### Startup / fixed costs (deliberately near-zero)

| Item | € / year | Note |
|------|---------:|------|
| VPS (Hetzner/Netcup) — Tailscale + Uptime Kuma NOC | ~€60 | ~€5/mo, shared across all clients |
| Betriebshaftpflicht (IT-service liability) | ~€120–240 | €10–20/mo |
| Legal AGB / Vertrag subscription (e.g. eRecht24-style) | ~€120 | ~€10/mo |
| Domain + email + simple site | ~€40 | |
| Gewerbeanmeldung (one-time) | ~€30 | one-off |
| Demo/showroom | **€0** | **own home is the showroom** |
| Tools/software (HA is free/open-source) | ~€50 | occasional |
| **Total fixed** | **~€400–500 / yr** | ≈ €35–45/mo |

**This is the model's superpower:** fixed costs are covered by **~2 Care clients or a single Blueprint.** Everything above break-even is essentially margin on the operator's time.

### Variable cost per project

| Tier | Variable cost | Components |
|------|--------------:|-----------|
| Blueprint | ~€10–30 | travel, PDF prep |
| HEMS | ~€30–60 | travel (2–3 visits), consumables; hardware is pass-through (not operator cost) |
| Full Retrofit | ~€80–150 | travel (several visits), staging consumables |

**Gross margin on the *service* component is ~90%+** because the only real input is time; hardware is pass-through and does not sit on the operator's books as a cost/risk beyond the handling markup.

---

## 6. Revenue Projections — Year 1 (solo, evenings/weekends)

**Conservative mix (capacity-checked against ~500 h/yr, A7):**

| Line | Qty | Unit service rev | Hours ea. | Service revenue | Hours used |
|------|----:|-----------------:|----------:|----------------:|-----------:|
| Blueprint | 8 | €450 | 5 | €3,600 | 40 |
| Energy Core (HEMS) | 6 | €1,560 | 18 | €9,360 | 108 |
| Full Retrofit | 2 | €5,190 | 50 | €10,380 | 100 |
| **Project subtotal** | **16** | | | **€23,340** | **248** |
| Care MRR (ramping to ~15 clients @ ~€29 by month 12) | | | | **~€2,600** (accumulated Yr-1) | ~40 |
| **Year-1 total turnover** | | | | **~€25,900** | **~290** |

*Hours ~290 billable + admin/marketing/travel fits comfortably within ~500 h/yr — there is headroom, but the § 19 ceiling (§7) is the real limiter, not time.*

> **Turnover note:** § 19 UStG counts **Gesamtumsatz** (gross receipts including hardware pass-through and handling), *not* just the service component. If hardware pass-through is invoiced through the operator's business, add ~€3,400 (HEMS ~€560×6) + ~€5,600 (Retrofit ~€2,800×2) ≈ **~€9,000** of hardware turnover on top → **total invoiced turnover could be ~€35,000.** See §7 — this is the single biggest ceiling risk, and it's a structural choice, not an accident.

### Year-1 revenue, service-only vs. all-in

| View | Turnover | vs. €25,000 ceiling |
|------|---------:|---------------------|
| Service + Care only (hardware bought by client directly) | **~€25,900** | **~€900 over** — just crosses |
| All-in (hardware invoiced through business) | **~€35,000** | **~€10,000 over** — clearly regular VAT |

**Design implication:** to *stay under* the ceiling in Year 1, either (a) have clients buy hardware directly on the operator's shopping list (removes ~€9k of turnover, keeps only ~€25.9k — still marginal), or (b) plan deliberately to cross it (§7). Given demand > capacity, **crossing is the healthy outcome** — the question is *when* and *how to price for it.*

---

## 7. Kleinunternehmerregelung (§ 19 UStG) — Implications

**The 2026 rule (post-2025 reform):**
- Stay a Kleinunternehmer if **prior-year Gesamtumsatz ≤ €25,000** *and* **current-year ≤ €100,000**.
- Cross **€100,000 mid-year → VAT applies immediately** from the crossing transaction (a sharp 2025-reform change; the old rule let you finish the year).
- **Gesamtumsatz includes hardware pass-through** if invoiced through the business — this is what pushes the all-in scenario (§6) over the line.

**Stay under vs. cross — decision logic:**

| Factor | Stay under €25k | Cross into regular VAT |
|--------|-----------------|------------------------|
| Client base | Mostly **private homeowners** (can't reclaim VAT) → your no-VAT price is a genuine ~19% discount | Any |
| Admin appetite | Wants minimal bookkeeping | Can handle Umsatzsteuer-Voranmeldung |
| Hardware handling | Push hardware to client-direct purchase to shrink turnover | Invoice hardware through business, **reclaim Vorsteuer** on your own tool/VPS/hardware buys |
| Growth | Genuine side-hobby cap | Wants to scale, add Care base, maybe go full-time |

**The core tension:** your customers are **private individuals** who *cannot* deduct VAT. So going VAT-registered means either (a) your effective prices rise ~19% (less competitive), or (b) you absorb the VAT out of margin. **Therefore: stay under €25k as long as the side-business is genuinely part-time.** Because demand outstrips capacity, the practical lever is **raising prices** (fewer, higher-value Tier 3 + Care) to keep turnover near the ceiling while maximizing per-hour value — rather than adding volume that forces VAT registration for little net gain.

**Trigger to switch deliberately:** when either (1) you want to go full-time/scale beyond ~€25k service revenue, or (2) hardware turnover alone forces it. At that point, invoice hardware through the business to reclaim Vorsteuer, and reprice Tier 3 to carry VAT gracefully (affluent Berger-segment tolerates it far better than the Stefan segment).

---

## 8. Pricing Psychology & Positioning (FFB-specific)

- **Anchor against KNX, always.** Every proposal states the comparison: *"A comparable KNX/Loxone system starts at €15,000–€25,000 and locks you to one vendor. This delivers the outcomes you care about — energy optimization, comfort, control — wirelessly, for a fraction, with no lock-in."* Your €4,800 Tier 3 looks like a bargain next to a €20k anchor.
- **Sell flat fees, never hours.** Affluent, time-poor clients buy *certainty and outcome*. An hourly rate invites scrutiny ("why did that take 3 hours?"); a flat "Energy Core €1,500" sells peace of mind.
- **Price as a competence signal.** In a 120–130% purchasing-power market, a €350 "cheap" quote *repels* the Berger/Stefan personas — it reads hobbyist. €1,500 reads professional. Do not compete on being cheapest.
- **Lead with digital sovereignty + control, not gadgets.** "Local-first, your data stays in your house, no cloud subscription, works if the internet is down." This resonates with the engineer-manager mindset common here.
- **Frame energy as *potential*, never a guarantee.** Say *"designed to shift consumption to your cheapest tariff hours and prioritize your own PV,"* — **never** *"you will save €X/year."* Guaranteed savings are legally and reputationally toxic and outside a Dienstvertrag's scope. Show the *mechanism* (PV-surplus charging, dynamic-tariff shifting), let the client infer the value.
- **Make Care feel like insurance, not an add-on.** "€29/month keeps it healthy and gives you a human on call" — reframes an ongoing cost as risk removal.
- **Blueprint-credit as a trust bridge.** Crediting the €450 Blueprint into a bigger tier removes the "am I hiring the right person?" risk and dramatically lifts upgrade conversion.

---

## 9. Break-Even & Sensitivity

**Break-even (fixed costs ~€450/yr):** covered by **one Blueprint** or **~2 Care clients**. Fixed-cost break-even is effectively *week one*. The meaningful question is opportunity value of time, not survival.

**Sensitivity — "only half the projected clients materialize":**

| Scenario | Projects | Service+Care turnover | vs. ceiling | Verdict |
|----------|---------:|----------------------:|-------------|---------|
| **Base (Year 1)** | 16 + ~15 Care | ~€25,900 | at/over €25k | Healthy; VAT decision point |
| **Half (–50% projects)** | 8 (4 BP / 3 HEMS / 1 Full) + ~7 Care | ~€12,500 | well under | Still strongly profitable |
| **Downside floor** | 4 Blueprints only + ~3 Care | ~€2,900 | far under | Still > break-even |

**Interpretation:** because fixed costs are trivial and all revenue is high-margin time, **there is essentially no loss-making scenario** — the downside is "earned less," never "lost money." Even the half-case (~€12.5k) is a strong side-income. The risk is entirely *upside management* (capacity + VAT ceiling), which is the good kind of problem.

**Key sensitivities to watch:** (1) hardware turnover quietly pushing Gesamtumsatz over €25k; (2) Care churn (model assumes retention — if it drops, the passive tail shrinks); (3) Tier 3 duration overruns (50h assumption is the softest — protect it with a change-order clause).

---

## 10. One-Page Pricing Sheet (client-facing extract)

> *Local-first smart home & energy management for your family home — no cloud lock-in, no €20k KNX.*

### Your Options

| | **Blueprint** | **Energy Core** | **Full Retrofit** |
|---|---|---|---|
| **For** | "Point me in the right direction" | "Optimize my energy & PV" | "Make my whole home smart — turnkey" |
| **You get** | Expert plan + device roadmap + tariff feasibility | HA hub + dynamic tariff + PV-surplus & heat-pump/wallbox automation + dashboard | Whole-home wireless retrofit, multi-room, polished dashboards, electrician coordination, 3 mo care |
| **Price** | **€450** | **€1,500** + hardware | **from €4,800** + hardware |
| **Hardware** | you buy from our list | ~€350–650, at cost | ~€1,500–3,500, at cost |
| **Timeline** | 1 week | 2–3 weeks | 4–8 weeks |

*Blueprint fee is fully credited if you upgrade within 90 days.*

### Keep It Running — **Care** from **€19/month**
Remote monitoring · secure updates · a human on call. *Because a smart home should stay smart.*

### Why us, not KNX?
> A comparable hardwired KNX/Loxone system starts at **€15,000–€25,000** and ties you to one vendor for life. We deliver the outcomes — comfort, control, and energy optimization — **wirelessly, locally, and without lock-in.** Your data stays in your house.

*All work on your 230V electrical installation is carried out by your certified Elektrofachbetrieb; we design, integrate, and commission the system.*

*Prices are net; as a Kleinunternehmer per § 19 UStG no VAT is charged. Estimates, not guarantees of energy savings.*

---

*End of internal planning document. Review the Assumptions Box (top) before quoting any figure externally.*
