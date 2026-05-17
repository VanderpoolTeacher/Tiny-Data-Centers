---
title: "Tiny Data Center Concept — Working Doc"
subtitle: "A direct Span/XFRA alternative — exploring the design space"
author: Michael Vanderpool
date_started: 2026-05-16
status: Working draft v0 — for iteration, not for sharing
---

# Tiny Data Center Concept — Working Doc

> **How to use this doc.** This isn't a product spec. It's a thinking surface. Sections 1–2 frame the strategic question. Section 3 maps the design dimensions where we'd choose to differ from Span. Section 4 sketches four distinct concept archetypes — each is a *bet*, not a recommendation. Section 5 names the open decisions and offers an opinion on each. Section 6 lists what we still don't know. Section 7 is the next set of work items.
>
> Mark up anything you disagree with; that's where the concept will actually sharpen.

---

## 1. The strategic question

**If we wanted to build something in the same neighborhood as Span/XFRA — small, distributed compute that solves the AI speed-to-power gap — but we deliberately chose a different shape, what would the most interesting alternative look like?**

Two sub-questions implicit in that:

1. *Where is Span structurally weak?* If we're targeting the same problem, our edge has to come from a real difference, not a marginal improvement.
2. *Where is the market actually underserved?* Solving the same problem for the same buyer (hyperscaler inference) is hard; solving an adjacent problem for an adjacent buyer might be easier.

This doc treats both as live.

### Where Span is structurally weak (the openings)

From the competitive landscape brief, the credible critiques of XFRA cluster on four axes:

- **Cluster topology.** 16 GPUs per node, separated by residential fiber, is fine for many inference workloads and terrible for tightly-coupled ones. A more clustered shape (multiple racks per site) opens up workloads XFRA can't take.
- **Service economics.** A truck-roll to one rack in one side yard is expensive. A model where one site holds 10 racks is fundamentally cheaper to operate per GPU.
- **Suitability ceiling.** ~30–40% of US homes plausibly qualify (internet, panel, willingness). At 80,000 nodes that's not binding. At any larger scale it is.
- **Ratepayer politics.** "Hyperscalers parking their load on residential ratepayers" is a real critique. State PUCs may or may not buy the headroom story.

Each of those is an opening for a differently-shaped concept.

### Where the market is actually underserved

From the same brief, the obvious unfilled slots:

- **No US heat-reuse player at scale.** Heata, Qarnot, Deep Green are all European. The US has none.
- **No tiny-DC for non-hyperscale buyers.** Span is selling to hyperscalers/neoclouds/AI companies. Schools, hospitals, government, manufacturers, regional ISPs — all of them want AI compute and none of them are anyone's target customer.
- **No tiny-DC packaged as disaster/resilience infrastructure.** Edge inference + on-site storage + backup power = a disaster comms node. Nobody is selling it that way.
- **No serious play on the rural-broadband edge.** WISPs and fiber co-ops are deploying in rural America. Tiny DCs co-located with their POPs could anchor local inference.

---

## 2. Strategic frame

I'm going to argue that the most useful frame is *"What if the unit isn't a house?"*

Span's choice of unit (one residential side yard) is what determines almost everything else: the power envelope, the workload mix, the channel, the politics, and the per-site economics. **If you change the unit, everything downstream changes.**

So this doc explores four candidate units:
- **A.** The unit is still a house, but the value proposition is heat-reuse, not power-headroom rental.
- **B.** The unit is a cell tower or telco hut, not a house.
- **C.** The unit is a co-op building (school, fire station, town hall, hospital) — civic infrastructure with a community benefit story.
- **D.** The unit is a small commercial parcel co-located with a solar/storage installation that already needs grid capacity built for it.

Each one beats Span on something different and loses to Span on something different. None of them are obviously right; the point of this doc is to make the trade-offs visible.

---

## 3. The design space — the dimensions we'd choose on

Six dimensions matter. For each, I'll lay out the spectrum and mark **where Span sits**.

### 3.1 Power source

| Option | Trade-off |
|---|---|
| Residential grid headroom (Span) | Free incremental capacity, regulatory uncertainty |
| Commercial grid (regular interconnect) | Normal, predictable, but loses the speed-to-power story entirely |
| Behind-the-meter solar + battery | Slower per site, but clean, scalable, no PUC fight |
| Behind-the-meter natural gas / SOFC | Fastest at scale (Bloom model), high opex, ESG questions |
| Stranded power (flared gas, curtailed renewables) | Crusoe model — only works near specific resources |
| District heat reclamation host (heat-out, electricity-in) | Heata/Qarnot/Deep Green model; host pays for heat in kind |

**Span:** residential grid headroom + optional behind-the-meter solar. *Open lane: behind-the-meter solar+battery as the primary play, with no grid headroom thesis at all.*

### 3.2 Workload

| Option | Trade-off |
|---|---|
| Hyperscaler AI inference | Span's target; competitive, high margin, demanding SLA |
| Frontier model training | Needs tight clusters; tiny DCs are wrong shape |
| Cloud gaming | Latency-sensitive, episodic load, growing |
| Batch / offline compute (rendering, scientific) | Heata's target; cheap, weak SLA, doesn't need low latency |
| Local/sovereign AI inference (state, fed, defense) | Underserved; price-insensitive; needs physical-security story |
| Edge AI for industrial buyers (manufacturing QA, agriculture, energy) | Needs vertical sales, harder to scale, defensible |
| CDN / content edge | Mature, Akamai/Cloudflare already won |

**Span:** hyperscaler inference + cloud gaming. *Open lane: state/fed/local-gov sovereign inference, or vertical industrial AI.*

### 3.3 Channel

| Option | Trade-off |
|---|---|
| Homebuilders (Span/Pulte) | Pre-installation in new construction; slow to compound |
| Existing residential retrofit | Direct-to-consumer; high CAC, slow per site |
| Utilities | Slow procurement, high credibility, regulatory cover |
| Telcos / WISPs | Existing footprint, existing power, slower decision cycles |
| Municipalities | Slow, sticky, civic story; useful for first deployments |
| Solar developers / EPCs | Co-deployment with new solar+storage; aligned incentives |
| Manufacturing / industrial integrators | Sticky, vertical, hard sales |
| Direct to hyperscaler (build-to-spec) | Single buyer, large contracts, dependence risk |

**Span:** homebuilders. *Open lanes: telcos/WISPs (most direct structural competitor anyway), municipalities (civic story), solar developers (aligned-incentive co-deployment).*

### 3.4 Hardware envelope

| Option | Per-site shape | Notes |
|---|---|---|
| 1U-class box (~1 kW) | Heata scale | Batch only, very cheap to deploy |
| Single rack (~10–20 kW) | Span scale | One node per site |
| 2–4 racks (~40–80 kW) | "Tiny pod" | Loses single-rack simplicity, gains real clustering |
| Shipping-container / micro-modular (~100–500 kW) | Crusoe Spark, Duos Edge | Now you're a modular DC vendor |
| Multi-container campus (~MW) | EdgeConneX | A regional DC, not a tiny one |

**Span:** one rack per site. *Open lane: 2–4 racks per site at a non-residential host (school, tower, civic building) — keeps tiny-DC speed but enables intra-site clustering for harder workloads.*

### 3.5 Economic model

| Option | Who pays whom | Notes |
|---|---|---|
| Compute resale (Span) | Compute buyer pays us; we pay host for power | Margin sits in compute-vs-power spread |
| Heat resale (Heata, Deep Green) | We pay for power; host gets heat free; compute buyer pays for compute | Two-sided value |
| Host-as-customer | Host buys/leases the box and runs their own workloads | School wants AI? Sell them a box. |
| Capacity-as-a-service to utility | Utility pays us a capacity payment for managed flex load | Verrus/Emerald-style |
| Hosting fee | Host pays us a flat monthly fee for a deployed compute pod that runs their own things + sells excess | Hybrid |
| Government contract | Annual contract with state/fed for sovereign inference capacity | Slow procurement; sticky revenue |

**Span:** compute resale, with host as the "power supplier." *Open lanes: heat resale (US), host-as-customer (vertical), capacity-to-utility (grid services).*

### 3.6 Geography / regulatory posture

| Option | Trade-off |
|---|---|
| Single state pilot (Span: NV/AZ) | Easy to tune regulatory story; slow to scale |
| Multi-state from day one | Complex tariff/PUC variation |
| Federal facilities only | One customer, one regulator, predictable |
| Off-grid / on tribal land | Sidesteps most state-level grid politics |
| International (Canada/UK) first | Lower regulatory complexity in single national markets |

**Span:** NV/AZ pilot, US-wide ambition. *Open lane: federal-facilities-only, or off-grid, or Canada-first.*

---

## 4. Four directional bets

Each one is a coherent set of choices across the six dimensions. None of them are obviously right; they're meant to be *distinct enough that picking between them clarifies what we actually believe*.

### Bet A: "Hearth" — heat-reuse for the US Northeast

> *The first US Heata. Compute heats hot water in homes that currently pay $0.30+/kWh for heat. The compute is incidental; the value is reclaimed heat.*

| Dimension | Choice |
|---|---|
| Power source | Residential grid (compute generates heat) |
| Workload | Batch / offline AI training, rendering, scientific compute |
| Channel | Utility energy-efficiency programs + insulation/HVAC installers |
| Hardware envelope | 1U-class (~1 kW) on the hot-water tank or in the basement |
| Economic model | Heat reclamation savings for host + compute resale to buyer |
| Geography | New England + NY, where heating costs are highest |

**Why it works.** Heating in the US Northeast is genuinely expensive ($2,000–4,000/yr per home is normal). Reclaiming that as a free byproduct of compute is a *consumer*-grade pitch, not a real estate one. It doesn't compete with Span — it serves a workload Span can't take (batch).

**Why it might not work.** Single-box compute is hard to differentiate from a hyperscaler renting a tiny VM. Utility energy-efficiency programs are slow. The market for batch compute is small and price-pressured.

**Span comparison.** Different workload, different value prop, different physics. Not a direct competitor — could plausibly coexist.

### Bet B: "Steeple" — tiny DCs at cell towers and telco huts

> *Take Span's pitch (small compute pods, distributed footprint, fast deployment) and put it on infrastructure that's already built to host equipment, has commercial power, has fiber, has security, and has a tenant relationship.*

| Dimension | Choice |
|---|---|
| Power source | Commercial grid via existing tower interconnect; optional BTM solar |
| Workload | Low-latency AI inference (consumer AI, AR/VR, autonomous driving) |
| Channel | Tower co-owners (American Tower, Crown Castle) + WISPs in rural |
| Hardware envelope | 2–4 racks per site (~40–80 kW) |
| Economic model | Compute resale + host fee to tower owner |
| Geography | Top 50 metro markets first, then rural WISP build-out |

**Why it works.** Cordovil's analyst critique of Span literally points to this as "the more instructive parallel." Towers/huts have power, security, fiber, and operators who already do site rounds. Per-site economics are way better than residential. No ratepayer politics.

**Why it might not work.** This is the obvious move and well-resourced players (AWS Wavelength, Verizon 5G Edge) are already on it. Tower co-owners want a cut. The buyer doesn't really care whether the box is at a tower or in a metro DC if both meet latency.

**Span comparison.** Directly competes on the same buyer. Wins on operability and security, loses on residential proximity for very-last-mile latency.

### Bet C: "Civic" — sovereign inference at municipal/county facilities

> *Sell a turnkey "local AI compute" box to schools, libraries, fire stations, town halls, hospitals, regional gov. The selling point isn't speed-to-power — it's data sovereignty and local control.*

| Dimension | Choice |
|---|---|
| Power source | Commercial grid via existing building service; optional BTM solar |
| Workload | Sovereign/local AI inference, school district AI, medical inference, gov workloads |
| Channel | Direct gov procurement + civic systems integrators |
| Hardware envelope | 1–2 racks per site (~20–40 kW) |
| Economic model | Annual contract (host-as-customer) + optional shared-capacity overflow to others |
| Geography | One state at a time, starting where state procurement is fastest |

**Why it works.** US schools and small munis cannot use most AI offerings because of data governance, COPPA/FERPA, HIPAA, IT staffing, and political sensitivity. A local box is a real answer. Government contracts are sticky and predictable. Nobody else is targeting this buyer directly.

**Why it might not work.** Government procurement is glacially slow. School IT budgets are small. Margin per site is low. The political "AI in schools" narrative is volatile.

**Span comparison.** Different buyer entirely. Not really a competitor; more like "what Span won't do."

### Bet D: "Confluence" — tiny DC co-deployed with new utility-scale solar+storage

> *Solar developers already have to build grid interconnections that are partly underused most of the day. Co-locating a tiny DC on the solar parcel uses that underutilization, gives the solar developer extra revenue, and gives the compute buyer cheap renewable-tagged inference.*

| Dimension | Choice |
|---|---|
| Power source | On-site solar + storage from the host project |
| Workload | AI inference (latency tolerant) + scheduled training during solar peak |
| Channel | Solar developers (NextEra, Invenergy, AES) + EPCs |
| Hardware envelope | 2–4 racks per parcel (~40–80 kW), scaling to 5–10 racks |
| Economic model | Solar developer gets capacity payment + share of compute revenue; compute buyer gets renewable-tagged inference at below-grid pricing |
| Geography | Solar-rich states with high interconnection queue: TX, AZ, NV, CA |

**Why it works.** Solar developers have a real problem (interconnection queues, curtailment) that compute can absorb. Buyers want renewable-tagged inference for ESG reporting. The compute is genuinely cheaper because it's stranded power. No residential politics.

**Why it might not work.** Solar developers are slow procurement targets too. The "renewable-tagged" premium might collapse as RECs and PPAs commoditize. Crusoe-adjacent players (and Crusoe itself) are likely to move here.

**Span comparison.** Different power source story, different channel, but same buyer. Likely to be more capex-efficient per MW than Span and easier to scale, but slower to start (depends on solar developers' deployment cadence).

---

## 5. Open decisions — and where I'd lean

There are seven big calls to make. For each I'll mark **where I'd lean** and *why*; treat these as starting opinions, not conclusions.

### Decision 1: Are we picking a workload that Span can take, or one Span can't?

**My lean:** *One Span can't.* The Span-can-take workloads (hyperscale inference, gaming) are crowded. The Span-can't workloads (training, batch, sovereign, industrial-vertical) are real markets with fewer competitors. *Bets A, C, and D all take this stance; B competes head-on.*

### Decision 2: Are we residential, commercial, or institutional?

**My lean:** *Institutional or commercial.* The residential channel is what gives Span its speed and its political risk. Commercial/institutional sites are slower to acquire but easier to operate, easier to insure, easier to defend. *Bets B, C, and D all take this stance; A stays residential but for a different reason (heat, not headroom).*

### Decision 3: Are we using "found" power or paying for power?

**My lean:** *Paying for power, with a clear off-take story that justifies it.* "Found" power (Span's headroom thesis) only stays found if the regulator agrees with you, and the regulator may not. Paying for power and having a buyer who values the *delivery* (low latency, sovereignty, renewable tag) is more durable. *Bets B, C, D pay for power; A reclaims heat (not the same thing).*

### Decision 4: Are we building hardware, or are we packaging someone else's?

**My lean:** *Packaging.* The hardware game is brutal and dominated by Nvidia, Dell, Vertiv. The defensible work is in the orchestration software, the deployment channel, the operational SLA, and the buyer relationship. Treat the box as a commodity wrapped around Dell/Supermicro reference designs and Nvidia silicon. *All four bets implicitly assume this.*

### Decision 5: Are we a product company or a services company?

**My lean:** *Services with a hardware shape.* Pure-product companies in this space (modular DC vendors) are competing with Schneider and Vertiv on margins. Pure-services companies (decentralized GPU networks) get commoditized fast. The interesting middle is *running* a fleet of tiny DCs as a service, owning the SLA, billing the compute buyer. That's what Span is doing, that's what Crusoe is doing.

### Decision 6: Are we owning the asset or financing it?

**My lean:** *Own it.* Span's "third-party-ownership like a solar PPA" model is the right structure — keeps the homeowner contract simple, keeps the compute economics clean, lets us capture residual value. But ownership requires balance sheet, which means real fundraising. The alternative (host owns, we operate) is a different business with different unit economics; worth deciding consciously.

### Decision 7: Are we contrarian on the AI cycle, or riding it?

**My lean:** *Mostly riding, but with a hedge.* The AI inference market is real and growing; that's the tailwind every concept in this doc depends on. But a concept that *only* works if 2030 inference demand grows 10× is fragile. The best concepts (C, D) have value even in a slower AI scenario — sovereign inference still matters, renewable-tagged compute still matters. Bet B is the most exposed to AI cycle compression.

---

## 6. Open questions — what we don't know yet

These are the questions that, if we answered them, would change which bet to pick.

1. **What is Span's actual unit economics?** $150/month homeowner cost is public; per-node revenue and operating margin are not. Without that we're guessing whether their model is real.
2. **What is the marginal cost of inference today vs. in 18 months?** If inference prices keep dropping, the margin pool for any of these concepts shrinks. If inference compute becomes scarce again (post-Blackwell allocation), they get easier.
3. **Will state PUCs let Span's tariff story stand?** If yes, residential headroom is a real category. If no, Bet B/C/D all benefit by comparison.
4. **What workloads actually need <50 ms latency to end users?** This determines whether "tiny DC near user" is a real advantage or a marketing claim. Real-time AR/VR, agentic chat, autonomous-vehicle inference: yes. Most other inference: no.
5. **What does a school district / state procurement officer actually want?** Bet C is a hypothesis; nobody has run the customer-development conversation.
6. **What does a solar developer's stranded-capacity calculation actually look like?** Bet D depends on numbers that aren't on any public page; needs a 1:1 with NextEra or Invenergy infrastructure people.
7. **Are there hardware constraints that make 2–4 racks per site dramatically harder than 1?** Cooling and weight (concrete pad? structural attachment?) might tip the per-site economics. Worth a conversation with Vertiv/Schneider on multi-rack outdoor enclosures.
8. **What's the regulatory/insurance posture for liquid-cooled GPUs at non-DC sites?** UL listing, fire code, glycol leak liability — all unsexy and all potentially blocking.

---

## 7. What to flesh out next

Concrete next moves, ranked by how much they'd sharpen the concept:

1. **Pick a primary bet (A, B, C, D) — or explicitly defer it for two more weeks of customer-development.** Picking is more valuable than thinking; defer only if there's a specific data point you're waiting on.
2. **Customer-development conversations for whichever bet leads.** Five conversations would do more for this concept than another fifty pages of research. Specifically:
   - Bet A: utility energy-efficiency program manager + one consumer-electronics retailer.
   - Bet B: business-development at American Tower or Crown Castle.
   - Bet C: CTO of one large school district + a state CIO.
   - Bet D: interconnection engineer at one large solar developer.
3. **Sharpen the unit economics for the chosen bet.** Capex per site, opex per site per year, revenue per site per year, payback period. A one-page model — even a wrong one — forces decisions.
4. **Map regulatory dependencies for the chosen bet.** What approvals, what insurance, what UL listings, what code.
5. **Identify the first two real partners.** Not logos for a deck — actual contacts who'd take a call.
6. **Decide what we're *not* building.** Explicit "out of scope" is as important as the scope itself.

---

## 8. Working notes / scratch

Use this section to dump thoughts as you go. It's intentionally messy.

- The "tiny DC" frame is starting to feel like the wrong frame. The unit isn't tiny — the *site* is tiny. The thing is more like "small site, full-spec compute."
- If we believe (Decision 7) that we're mostly riding the AI cycle, then the concept that's *most insulated* from a cycle dip is the one that benefits even without aggressive AI growth. That biases toward C and D over B.
- Bet A and Bet D could combine: heat reuse in cold-climate solar + storage co-located sites is interesting but probably too complicated for a v1.
- The "Span sells compute, host gets power free" model is *brilliant* but only works because Span is paying retail residential rates and reselling at hyperscaler rates. The spread matters and the spread may compress.
- Counter-question worth holding: would we *actually* build this, or are we researching to invest / write / advise? The right concept differs by audience.

---

## Sources

This concept doc builds on prior research; see:
- [span-xfra-research-brief.md](./span-xfra-research-brief.md) — the Span/XFRA primer
- [span-xfra-competitive-landscape.md](./span-xfra-competitive-landscape.md) — competitive landscape and adjacent solutions
