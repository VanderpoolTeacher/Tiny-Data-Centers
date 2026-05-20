---
title: "Span XFRA — Investor & Strategic-Partner Report"
subtitle: "Consolidated analysis of the distributed AI data center thesis, with a focused view on Northwest Ohio"
author: Michael Vanderpool
date: 2026-05-20
status: Consolidated v1
classification: For investor / strategic-partner distribution
---

# Span XFRA — Investor & Strategic-Partner Report

*Evidence rating throughout this report:* **[S]** sourced directly from Span;
**[T]** sourced from a third party with named attribution; **[D]** derived or
computed in this report from sourced inputs; **[I]** inferred without direct
evidence and treated as hypothesis.

---

## 1. Executive summary

**Span XFRA is the first credible attempt to convert latent residential
electrical capacity into saleable AI inference capacity at hyperscale-grade
hardware spec.** Each node is a Dell PowerEdge box with 16× Nvidia RTX PRO
6000 Blackwell GPUs, 4× AMD EPYC CPUs, 3 TB of DDR5, direct-to-chip liquid
cooling, and a ~15–16 kWh whole-home battery, drawing ~19.2 kW continuously
from a host's 240 V residential service. Span pays the host's electric and
internet bills (a flat ~$150/month, sometimes zero) and sells the compute to
hyperscalers, neoclouds, and AI-native buyers. A 100-home, ~1.25 MW pilot
ships in Q3 2026 with PulteGroup as the new-construction channel; Span has
publicly floated 80,000 nodes nationwide and >1 GW of annual deployment
capacity by 2027 **[S]**.

**The thesis is investable because three structural conditions line up at
once.** Centralized data-center interconnection queues now run 5–7 years
**[T]**; public opposition to greenfield hyperscale campuses is rising; and
the political story Span tells utilities and PUCs — *"the distribution grid
already runs at 40–45% utilization; we are putting compute on the headroom"*
— is the most fundable narrative in DC infrastructure right now. The hardware
is conventional and shippable. The Nvidia / Dell / Eaton / Pulte partnership
stack legitimizes the product. The unit economics, on a derived basis,
can clear. None of those facts are in serious dispute. What *is* in dispute,
and what determines the size of the outcome, is whether (a) at least one
public-utility commission approves a tariff that lets Span pay below retail
for marginal kWh, (b) at least one hyperscaler signs a multi-year anchor
contract at edge-premium pricing, and (c) the orchestration layer delivers
hyperscaler-grade SLA across a residential fleet. The next 18 months — pilot
results, first hyperscaler contract, first major PUC ruling — will resolve
most of the load-bearing uncertainty.

**Northwest Ohio is structurally the strongest US geography in which to play
the distributed-compute thesis.** Meta has already committed $800M and 350 MW
to a Wood County campus that breaks ground in 2025 and goes online in 2027
**[T]** — confirmed hyperscale-tier demand in this exact footprint. AEP
Ohio's data-center tariff (PUCO-approved July 2025) applies *only* to new
loads above 25 MW aggregate and locks subscribers into 85% take-or-pay for up
to 12 years **[T]**. XFRA nodes at ~19 kW are three orders of magnitude below
the threshold and are billed on residential tariffs. The arbitrage door is
real and currently open. AEP Ohio residential power runs ~9.94¢/kWh — below
the NV/AZ benchmark of $0.13/kWh used in Span's own pilot economics. The
result is a per-node gross margin band of roughly $128K (61%) in NW Ohio
versus $113K (57%) in NV/AZ and $89K (45%) in California **[D]**. A
1,000-node regional pilot at base-case pricing implies ~$210M of annual gross
revenue and ~$128M of regional gross margin before corporate overhead. Even
the bear-case ($170K/node) clears $170M of regional revenue.

---

## 2. The Northwest Ohio opportunity

### 2.1 Demand has already arrived

The single most important fact for any Northwest Ohio investment thesis is
that **hyperscale-tier AI compute demand in this footprint is no longer
theoretical.** Meta announced an $800M, 350 MW data center in Middleton
Township, Wood County — roughly 20 miles south of Toledo — in April 2025.
Ground broke in 2025; the campus targets online status in 2027. The
JobsOhio / Regional Growth Partnership / Meta announcement is direct and
confirmed; Meta lists it publicly as its 24th US data center and 28th
globally **[T]**.

The Meta campus is not the only live prospect in the geography. Three other
sites are in active motion as of late 2025:

- **Oregon, OH (Lucas County):** 170 acres sold November 2024 for $17.3M
  with up to eight buildings planned.
- **Waterville Township (Lucas County):** A developer eyeing 1,000–1,400
  acres. The township imposed a 12-month moratorium on December 17, 2025.
- **Lucas County:** Commissioner Pete Gerken proposed a 90–120 day countywide
  pause in December 2025.

The political signal is unambiguous: hyperscale-scale builds are running
into local opposition in exactly the same footprint where hyperscale demand
is landing. That dynamic is *structurally favorable* for distributed and
residential models that bypass the hyperscale-site permitting fight
entirely. A 19 kW pod on a side yard is not the thing being moratoriumed in
Waterville.

### 2.2 The AEP Ohio data-center tariff is an arbitrage door

On July 9, 2025 the Public Utilities Commission of Ohio approved AEP Ohio's
data-center tariff; it became effective July 23, 2025. The tariff applies
*only* to new loads above **25 MW aggregate** and imposes structural
requirements that fundamentally reshape the economics for a hyperscale
buyer **[T]**:

- **85% take-or-pay** of subscribed capacity for up to 12 years, regardless
  of actual usage.
- **4-year maximum** load ramp.
- **8-year minimum** contract term.
- **3-year minimum-charge** exit fee.

XFRA nodes are individually ~19 kW — three orders of magnitude below the
25 MW threshold — and are billed at residential rates. In the same regulatory
geography, two compute footprints face wildly different cost structures: a
hyperscaler pays for 85% of subscribed capacity for 12 years regardless of
utilization; an aggregator of distributed residential nodes pays only for
energy actually used. This is the single strongest defensible NW Ohio thesis
point. It also explains why a hyperscaler signing the AEP tariff might
*itself* want exposure to a distributed-compute layer in the same region as
a portfolio hedge.

The standard ratepayer-advocate objection — that distributed compute "parks
hyperscaler load on residential ratepayers" — is real and worth pricing in.
Span's pre-emptive defense leans on the Brattle Group's *Untapped Grid*
framing: that adding 7–12 kW of continuous controllable load behind the
meter *increases* kWh sold over the same distribution capex base, so per-kWh
delivery costs drop. Whether PUCO accepts that framing on its first
contested filing is one of the watch-list items in §9.

### 2.3 Power here is actually cheap

| Utility | Residential rate | Window |
|---|---|---|
| AEP Ohio | 9.94 ¢/kWh | Jun 2025 – Aug 2026 |
| Toledo Edison | ~9.5–9.8 ¢/kWh | 2025 |

Both rates are *below* the $0.13/kWh that Span's pilot economics assume for
the Southwest. At ~19.2 kW continuous and ~134,500 kWh/yr per node, the
per-node power line moves from ~$17.5K in NV/AZ to **~$13K in NW Ohio** — a
$4.5K margin pickup before any other input changes **[D]**.

### 2.4 Per-node P&L: NW Ohio vs. comparison geographies

| Line item | **NW Ohio** | NV/AZ (Span pilot) | California | Source |
|---|---|---|---|---|
| Power | **$13K** | $17.5K | $41K | Residential retail × 134,500 kWh/yr |
| Internet | $1K | $1K | $1K | $80/mo gigabit fiber |
| Operations | $7K | $7.5K | $8K | Truck rolls, monitoring, insurance |
| Capex amortization (5 yr) | $61K | $61K | $61K | $310K hardware ÷ 5 yr |
| **Cost floor** | **~$82K** | $87K | $111K | sum |
| Target revenue (base) | $210K | $200K | $200K | derived; see §5 |
| **Gross margin** | **$128K (61%)** | $113K (57%) | $89K (45%) | |

NW Ohio is structurally the strongest market in this comparison. The base
case is not heroic: it assumes a $2.50/GPU-hour wholesale price (mid-band
of public retail rates discounted to wholesale), 85% inference utilization,
and standard truck-roll cadence. The bull case ($280K/node, ~$198K margin)
requires only a 1.5x edge-latency premium and PUCO blessing of residential
aggregation. The bear case ($170K/node, ~$88K margin) assumes no edge
premium and lower utilization — and still clears a $170M regional revenue
line at 1,000 nodes.

### 2.5 What the region brings beyond the numbers

Beyond raw economics, Northwest Ohio carries a small cluster of structural
advantages that matter for execution speed:

- **First Solar's CdTe PV supply chain at Perrysburg**, giving Bet D
  (co-deployed solar) an unusual local anchor.
- **A workforce already absorbed by the Meta build.** IBEW Local 8 reports
  Journeyman Inside Wireman calls going unfilled daily as the Meta campus
  ramps; deploying distributed compute leverages the same trained pool.
- **UToledo PVIC and BGSU College of Engineering and Innovation** as
  technical validation partners.

The investor framing reduces to a single number: *$210K/node base × 1,000
nodes = $210M/yr regional gross revenue.* Even discounted to the bear case
the order of magnitude clears the cost of running the six conversations
needed to test it.

---

## 3. What XFRA is

### 3.1 The company

Span (legal name SPAN.io, Inc.) was founded in 2018 in San Francisco by
**Arch Rao**, who previously led Tesla Energy product. The company is best
known for a smart electrical service panel that gives per-circuit visibility
and dynamic load control. As of 2026 Span has raised >$285M including a $75M
strategic investment from **Eaton** and is closing a Series C reported at
~$176M (with $163M of equity already sold as of February 2026) **[T]**.

**XFRA** ("eks-fra") was announced April 13, 2026 at Latitude Media's
Transition-AI conference, with **Nvidia** as initial launch partner
(silicon), **Dell** as server hardware provider, and **PulteGroup** — the
third-largest US homebuilder — as the new-construction deployment channel.
A white paper is published at xfra.ai. Span explicitly positions XFRA as
*complementary* to centralized data centers: training stays in hyperscale
campuses; inference and other latency-sensitive workloads (cloud gaming,
autonomous-driving inference, medical-image diagnostics) move to the
grid edge **[S]**.

### 3.2 The node

| Component | Spec | Source |
|---|---|---|
| Chassis | Dell PowerEdge in outdoor enclosure (~HVAC condenser size) | Span; Network World |
| GPUs | 16× Nvidia RTX PRO 6000 Blackwell Server Edition | Span; pv-magazine |
| CPUs | 4× AMD EPYC | pv-magazine; Network World |
| Memory | 3 TB DDR5 | pv-magazine; Network World |
| Networking | 24-port gigabit switch; fiber uplink | pv-magazine; Data Center Richness |
| Cooling | Direct-to-chip liquid; 35,000 BTU (~3-ton) heat pump | Technology.org; Data Center Richness |
| Acoustics | ~60 dB operating | Data Center Richness; Network World |
| Battery | ~15–16 kWh whole-home | Data Center Richness; Technology.org |
| Hardware BOM | >$250K of compute hardware per node | Network World analyst pricing |

A derived check on price using street rates: RTX PRO 6000 ≈ $9–10K × 16 =
$144–160K; EPYC ≈ $8.5–14K × 4 = $34–56K; 3 TB DDR5 DC-grade ≈ $90–105K;
chassis, cooling, networking, enclosure, install ≈ $40–80K. **Total hardware
≈ $310–400K per node [D].** Network World's quoted ">$250K of compute
hardware" is consistent with the lower-bound subset.

### 3.3 The power story

Span's claim: ~80 A continuous at 240 V ≈ **19.2 kW**, sized to fit inside
a 200 A residential service envelope alongside the home's own loads
**[S]**. A 16× Blackwell server at full load draws roughly 9.6 kW; 4× EPYC
adds 1.0–1.6 kW; memory ~150 W; networking and chassis overhead ~200 W.
IT load thus runs ~11–12 kW. Adding a 3-ton heat-pump cooling loop at ~3 kW
electrical and battery-charging headroom at ~3–4 kW gives **17–19 kW total
facility draw [D]** — at the top of the plausible band and consistent with
Span's 19.2 kW figure.

A Latitude Media report describes the 100-home / 1,600-GPU pilot as
"1.25 MW of compute capacity." That works out to 12.5 kW per node, which
matches *IT-only* draw — not total facility draw. The 19.2 kW figure is the
*electrical service allocation*. Both numbers are internally consistent if
read carefully.

The political payload of the power story sits in one sentence from CEO Arch
Rao: *"The existing distribution network operates at only 40 to 45%
utilization, nominally."* Span's panel measures real-time per-circuit draw,
treats the XFRA pod as a managed always-on load, and curtails opportunistically
when the host's appliances ramp. The included whole-home battery buffers
short spikes, supplies the home during outages, and lets the pod participate
in utility demand-response events instead of curtailing the homeowner. Span
is in active conversations with utilities about "innovation in the tariff
model" — i.e., the rate Span pays for XFRA-consumed kWh may diverge from
standard residential retail **[S]**.

### 3.4 The homeowner offer

- Smart panel + XFRA pod + whole-home battery installed at **no upfront cost**.
- Flat **~$150/month** that covers the host's full electric *and* internet
  bill — Span pays both utilities directly.
- In the highest-value siting (cheap power + valuable inference latency +
  solar), the company has floated *free electricity and free internet*.
- The structural analog Span uses internally: a rooftop-solar PPA, except
  Span owns compute assets instead of panels.

### 3.5 Deployment trajectory

| Phase | Date | Scope | Channel |
|---|---|---|---|
| In-house prototype | Pre-2026 | Undisclosed paying customers | Direct |
| Proof of concept | Q3 2026 | **100 new-construction homes / ~1.25 MW / ~1,600 GPUs** in NV or AZ | PulteGroup |
| Scale ramp | 2027 | >1 GW annual deployment capacity | Multiple homebuilders + utility partners |
| Commercial XFRA | Early 2027 | Offices and small commercial buildings | TBD |
| Long-term stated goal | Unspecified | **~80,000 nodes nationwide** | Distributed |

The new-construction-first choice is deliberate. Builder-channel deployment
lets Span pre-wire the panel, conduit, battery pad, and liquid-cooling drain
in one trip and pre-bundle the homeowner contract before move-in. Retrofit
is technically possible but slower, more expensive, and runs into the
older-residential-service envelope problem that the pilot deliberately
sidesteps.

### 3.6 Headline unit-economics claim

- **Build cost:** ~$3M per MW of compute, vs. ~$15M/MW for a centralized
  100 MW facility — roughly **1/5 the capex per MW [S]**.
- **Time-to-power:** ~**6 months** to stand up the equivalent of a 100 MW
  facility (≈8,000 nodes), vs. 3–5 years for greenfield. This is the
  "speed-to-power" framing the marketing leans into.
- **Per-node asset-value benchmark:** Abe Yokell (Congruent Ventures) frames
  each node as ~$1M in asset value, derived from Nvidia's $50B/GW capex
  benchmark × 1 GW ÷ 50,000 nodes **[T]**.

---

## 4. Technical viability

### 4.1 Hardware (low risk)

XFRA's bill of materials is a conventional enterprise AI inference server in
an industrialized outdoor enclosure. Every component is shipping product;
the integration is non-trivial but is not research-stage. Dell, Nvidia, and
Eaton-grade enclosure design are all mature. Hardware risk is **low**.

### 4.2 Power envelope (low for new construction, high for retrofit)

The 19.2 kW claim is technically defensible for new-construction homes with
a Span panel. For retrofit homes with older 100 A or 150 A service, the
envelope is much tighter and may not work — which is why the pilot is in
new-construction homes only. The retrofit question is deferred, not solved.
It matters at the 5M-home scale; it does not matter at the 80,000-node scale.

### 4.3 Cooling and acoustic (low-to-medium risk)

Direct-to-chip liquid cooling is now standard for high-density AI racks. A
3-ton heat pump is a normal residential HVAC component; rejecting ~12 kW of
IT heat is well within its design envelope. The 60 dB target is below most
municipal residential nuisance ordinances (which typically set 55–65 dB
nighttime limits at the property line), but Span has not published
distance-attenuated numbers — the 60 dB figure is *at the unit*, not at the
neighbor's window.

**Risk flag.** Long-term reliability of glycol/water loops in residential
climates (freeze cycles, leaks, biological fouling) is the unsexy maintenance
question. Glycol leak liability at a residential site is a real insurance
question and Span has not publicly addressed it.

### 4.4 Networking (medium risk)

A 1 Gbps uplink is sufficient for inference traffic to and from one node
but *insufficient* for large model-weight movement, KV-cache sharing across
nodes, or any tight-coupling workload. This is consistent with Span's stated
workload positioning (inference, not training). At national scale, fiber
availability becomes a real screen on the addressable home base — Davies
(Utah State) estimates a suitability ceiling of ~30–40% of US homes,
partly driven by fiber.

### 4.5 Orchestration (most novel, least documented)

Span's claim: workloads are scheduled and routed across nodes based on
latency requirements and available energy capacity; nodes drain when a host
has an outage or panel headroom drops. The orchestration layer is the single
most technically novel piece of the system. It is also the least publicly
documented. Span has not disclosed latency targets between workload arrival
and node selection; the partial-failure model (e.g., 200 nodes simultaneously
lose internet during a regional outage); how buyer SLAs are translated into
orchestrator policy; or whether GPU memory state is checkpointed and migrated
or workloads simply restart on a new node.

These omissions are not red flags by themselves — companies don't publish
their orchestrator design pre-launch. But they mean the orchestration story
is **assertion, not evidence**, at this point. Risk grade: medium-high.

### 4.6 Technical viability — summary

| Component | Risk | Notes |
|---|---|---|
| Hardware | Low | Mature parts, conventional integration |
| Power envelope | Low (new) / High (retrofit) | Pilot avoids retrofit risk by selecting new-build only |
| Cooling | Low to medium | Standard tech; residential maintenance and insurance unproven |
| Acoustics | Low | Likely within ordinances; no distance-attenuated data |
| Networking | Medium | Constrains scale-out beyond fiber-pre-pulled footprint |
| Orchestration | Medium-high | Most novel; no public evidence yet |

**Verdict.** Technical viability is plausible and Q3 2026-deliverable for
the 100-home pilot. The unverified pieces only start to matter at the
1,000-to-10,000 node scale.

---

## 5. Business viability and unit economics

### 5.1 The four-variable model

Span's pitch reduces to four numbers per node:

- **R** — annual compute revenue from selling node capacity to the buyer
- **C_pwr** — annual cost of paying the host's electricity bill
- **C_net** — annual cost of paying the host's internet bill
- **C_op** — annual amortized capex plus operating cost (truck rolls,
  software, support, insurance)

Per-node margin ≈ R − (C_pwr + C_net + C_op). The model only works if R is
significantly larger than the sum.

### 5.2 Each term, derived

**C_pwr.** 19.2 kW × 8,760 hr × ~80% effective utilization ≈ 134,500 kWh/yr.
At Nevada/Arizona residential retail of ~$0.13/kWh ≈ **$17,500/yr**. At
California residential of ~$0.30/kWh ≈ $40,300/yr. **At AEP Ohio
9.94¢/kWh ≈ $13,000/yr.** The Southwest pilot picks the cheap end
deliberately; Ohio is cheaper still.

**C_net.** Residential gigabit fiber ≈ $80/month × 12 = **~$960/yr**. Span
pays the host's bill directly; some margin to the ISP, but small.

**C_op.** Unknown publicly. Truck roll to one rack at a residential site at
$300–500 per visit, with 4–6 visits per year, ≈ $1,200–3,000/yr. Insurance,
software, monitoring not published; estimated total **$5,000–10,000/yr**.

**Capex amortization.** $310–400K hardware ÷ 5 years (aggressive but
standard for GPU depreciation under AI-cycle pressure) ≈
**$62,000–80,000/yr**.

**Cost floor (Southwest):** ~$85,000–93,000/yr per node.
**Cost floor (NW Ohio):** ~$82,000/yr per node.
**Cost floor (California):** ~$108,000–116,000/yr per node.

### 5.3 The revenue side — three independent back-solves

The challenge is that Span has not published per-node revenue. Three
independent back-solves converge in the same band.

**Method A — retail GPU-hour pricing discounted to wholesale.** Median
retail rent for RTX PRO 6000 Blackwell on the open market is $2.25–$3.56
per GPU-hour as of May 2026 **[T]**. Span sells wholesale to hyperscalers,
not retail to GPU renters — apply a standard wholesale-to-retail discount of
60–70%. Inference utilization typically lands at 80–90% (versus 60–70% for
training):

| Scenario | $/GPU-hr | Utilization | Wholesale ratio | Annual/node |
|---|---|---|---|---|
| Bear | $2.00 | 70% | 0.55 | $108K |
| Base | $2.50 | 85% | 0.65 | **$193K** |
| Bull | $3.00 | 90% | 0.70 | $264K |

Formula: $/GPU-hr × 16 GPUs × 8,760 hrs × utilization × wholesale ratio.

**Method B — Congruent Ventures asset-value back-solve.** Yokell's $1M
asset-value-per-node framing, applied at a typical data-center asset yield
(15–25% gross revenue / asset value), lands at **$150K–$250K/yr**.

**Method C — Span's own framing.** The CEO has stated revenue "exceeds the
cost of the XFRA system itself" without disclosing a number. Span quotes
$3M/MW for XFRA capex vs. $15M/MW for traditional builds; at 19.2 kW/node,
$3M/MW implies *system* capex of ~$58K per node. If revenue exceeds that on
a yearly basis, it is a hard floor — and Methods A and B both land well above
it.

**Convergence.** The three methods cluster at **$180K–$230K per node per
year**. The base case used throughout this report is **$210K/yr**.

### 5.4 Where the model gets fragile

| Sensitivity | Direction | Notes |
|---|---|---|
| GPU resale price compression | Negative | Blackwell-successor releases that cut inference cost-per-token by 50% drag R sharply |
| Residential-rate increases without offsetting tariff innovation | Negative | High-rate states get unprofitable fast |
| Hyperscaler reluctance to pay edge premium | Negative | If buyers prefer Crusoe's stranded-power compute at lower price |
| Channel slowdown (Pulte ramp) | Negative | Pulte ≈ 7–8% of ~1M annual US single-family completions |
| Single anchor hyperscaler signed at scale | Positive | Removes most R-side uncertainty |
| Inference-latency premium for consumer AI workloads materializes | Positive | AR/VR, agentic chat, autonomous-vehicle inference |
| PUC tariff innovation that lets Span pay below-retail for marginal kWh | Positive | The most leveraged single variable |

### 5.5 Why a hyperscaler would pay the edge premium

The math requires hyperscaler-tier pricing roughly equivalent to $24–30 per
GPU-hour fully-loaded **[D]**, against decentralized network prices of
$1.50–$3.50/GPU-hr (io.net) and hyperscaler prices of $5–15/GPU-hr for
similar-class GPUs. The premium has to be justified by one of:

- **Latency.** Inference within tens of milliseconds of the end user — a
  metro DC can match this (~5–20 ms to consumer ISPs); a Texas hyperscale
  campus cannot (~30–80 ms to East Coast users).
- **Availability.** Capacity that can be turned on in six months, not three
  to five years. The speed-to-power argument.
- **Renewable proximity / political optics.** Compute deployed at
  residential addresses generates a different ESG story than a 200 MW
  campus near a substation.

The first two are real and probably worth a premium. The third is soft.

### 5.6 Business viability — verdict

The economics can work at pilot scale in the Southwest and at modest scale
in NW Ohio with conservative assumptions. They **almost certainly do not
work** in California without tariff innovation. They **may or may not work**
at 80,000-node national scale depending on inputs not currently public.

The story is not implausible. It is, however, *load-bearing on three things
Span has not published*: orchestrator efficiency, anchor-tenant pricing, and
utility tariff treatment.

---

## 6. Competitive landscape

There is **no other company in the US putting a 16-Blackwell-GPU pod on the
side of a single-family home.** In that exact niche, Span has the field to
itself today. But XFRA is one answer to a much larger problem — *AI compute
is bottlenecked by power and time-to-power, not by silicon* — and there are
at least eight categories of solution chasing the same gap. They differ on
where the compute lives, who pays for the power, what workload they target,
and how they get around the grid.

### 6.1 Direct peers: distributed compute in homes and small buildings

**Heata (UK).** A ~1 kW compute server bolted to a domestic hot-water
cylinder, dumping waste heat into the tank — up to ~4.25 kWh/day of hot
water per host, saving up to £340/yr. Sells compute via Civo; works with
British Gas. Offline batch only. Roughly two orders of magnitude smaller
per node than XFRA.

**Qarnot Computing (France).** Founded 2010. Liquid-cooled servers feeding
district-heating loops or building hot water (~95% heat reuse). CPU/HPC
focus, French scale, ~$55M raised. The spiritual ancestor of "compute as a
heat source." Not a serious threat.

**Deep Green (UK).** Immersion-cooled HPC tubs at UK leisure centres'
swimming pools, ~28 kW per site. Backed by £200M from Octopus Energy. Closer
to XFRA on cooling and per-site power, but B2B-to-leisure-centre, not
residential, and general cloud workloads, not premium AI inference.

### 6.2 Modular / prefab data centers

The "speed-to-power middle ground" — same workloads as XFRA, very different
unit size. Market valued at ~$29–33B in 2025.

- **Schneider + Compass:** prefabricated white-space pods, first units fall
  2025; ~30% faster build, ~3 months sooner revenue.
- **Vertiv MegaMod CoolChip:** high-density liquid-cooled modular DC for AI;
  ~50% faster delivery than traditional.
- **Crusoe Spark:** 100s of kW to 100s of MW per unit, ~3 months
  time-to-power. New Spark Factory live in Brighton, CO; Energy Vault signed
  for up to 25 MW; Redwood Materials expanded from 4 to 24 Spark units.
- **Duos Edge AI:** 55 ft × 12.5 ft modular pods for edge AI inference.

These compete with Span on *time-to-power* but not on *power source* — they
still need a real interconnection.

### 6.3 Edge colocation

**EdgeConneX** (North America, Europe, APAC; €500M expansion late 2024) and
**EdgePresence** ($50M expansion 2024) own metro/regional edge sites and
operate them as IaaS. They compete on the same latency story as XFRA but
buy commercial power through the standard interconnection queue.

### 6.4 Hyperscaler and telco edge boxes

AWS Outposts, Azure Stack Edge, Google Distributed Cloud Edge, Verizon
5G Edge, AT&T edge, AWS Wavelength. Edge zones planted in telco facilities
and customer premises. Outposts mindshare actually *declined* in April 2026
(9.3%, down from 15.4% YoY); Azure Stack Edge dropped from 28.9% to 14.6%.
The appliance model is losing traction against hyperscaler edge zones and
regional DCs.

The analyst Alex Cordovil (Dell'Oro), in his XFRA assessment, specifically
flagged this category as *"the more instructive parallel"* to Span — telcos
already have power, fiber, security, and a distributed-node structure, but
"still wrestle with running compute across a small number of GPUs per site."

### 6.5 Behind-the-meter generation

If interconnection is the bottleneck, skip it. Generate on-site.

- **Crusoe Energy:** 1.2 GW Stargate campus in Abilene, TX, energized within
  ~1 year of breaking ground. Fast Company 2026 Most Innovative.
- **Bloom Energy + Brookfield:** $5B partnership to put SOFC capacity across
  AI factories worldwide. Bloom doubling annual manufacturing from 1 GW to
  2 GW by end-2026; Q1 2026 revenue $751M, up 130% YoY. Bloom's 2026 Power
  Report: 32% of US data centers plan to operate fully off-grid on SOFC by
  2030, up from 22% six months earlier.
- **FluxCore:** modular DC directly powered by on-site generation.

The category as a whole closed $7.65B in binding deals from late 2025 to
early 2026 **[T]**.

### 6.6 Grid-flex orchestration

A different shape entirely: don't deploy new compute — make existing AI
factories behave like flexible loads.

- **Emerald AI + Nvidia:** "Emerald Conductor" software ramps AI workloads
  in response to grid signals. Phoenix demo via EPRI's DCFlex: ramped down
  in 15 minutes, sustained a 25% reduction for 3 hours. Combined with
  Nvidia's DSX Flex, claims to unlock up to **100 GW** of new US grid
  capacity without building new plants **[T]**.
- **Verrus** (Sidewalk Infrastructure spinout): testing at NREL's 70 MW DC;
  shifts 100% of a DC's power demand from grid to on-site within one minute
  of a utility request.

Span and Emerald are pitching the same political story — grid utilization is
the cheap unlock — from different angles. A hyperscaler could plausibly use
both.

### 6.7 Decentralized GPU marketplaces

Software-only distribution layer over already-installed GPUs.

- **io.net:** $1.50–$3.50/GPU-hr; 15–63% discount on AWS-comparable
  configurations.
- **Akash Network:** launched AkashML for managed AI inference.
- **Render Network:** 600+ open-weight models on its AI Compute Subnet.

The decentralized GPU sector handled an estimated **$200M in annualized
protocol revenue in early 2026 [T]**. Different product, same thesis. They
threaten Span on the price-sensitive long tail, not on hyperscaler-grade
inference.

### 6.8 Where Span actually wins, and where it doesn't

**Span wins on:**

- **Speed to incremental capacity in a specific metro.** Six months to
  stand up the equivalent of a 100 MW DC, no interconnection queue.
- **Latency proximity to consumers.** For consumer-facing inference (AI
  chat, gaming, on-device assistants), one residential hop from the end
  user is a real advantage telco edge can match but modular prefab cannot.
- **Capex per MW.** ~$3M/MW vs. ~$15M/MW greenfield.
- **Political story.** "Using grid headroom that's already there" is
  cleaner to a PUC than "building a 200 MW campus with a new substation."

**Span loses or is at parity on:**

- **Cluster topology for frontier training.** Modular prefab and BTM Crusoe
  beat XFRA on tightly-coupled workloads. Span concedes this.
- **Per-GPU-hour cost.** Decentralized networks beat enterprise pricing by
  60–90% for workloads that tolerate weak SLA.
- **Operability and service economics.** A truck roll to one residential
  side yard is far more expensive than a tech walking between racks.
- **Physical-security trust.** Telco sites and BTM generation have decades
  of carrier-grade operating practice.
- **Capacity ceiling.** At 30–40% household suitability, Span's plausible US
  ceiling is single-digit GW.

**Most direct structural threats, ranked:**

1. **Telco edge (Verizon, AT&T, AWS Wavelength).** Same distributed shape,
   existing fiber + power + security. The most credible direct substitute.
2. **Crusoe Spark + Edge Zones.** Closest factory-built tiny-DC product,
   three-month time-to-power, commercial parcels rather than residences.
3. **Behind-the-meter + Emerald AI combo.** A hyperscaler that pairs Bloom
   SOFC with Emerald's grid-flex gets most of Span's speed-to-power benefit
   without residential channel friction.
4. **Modular prefab (Schneider+Compass, Vertiv).** Cuts greenfield to
   ~16 weeks.
5. **Heata / Qarnot / Deep Green.** Useful cohort, not a competitive
   constraint.
6. **Decentralized GPU networks.** Cost ceiling, not a strategic threat.

---

## 7. Strategic positioning and risk inventory

### 7.1 The position Span is occupying

XFRA's position is **"first and only residential-channel distributed compute
at hyperscaler-grade hardware spec."** Three things define it:

1. **Channel exclusivity.** PulteGroup is the #3 US homebuilder; Span's
   relationship is the first builder-distributor for compute at this scale.
2. **Power thesis.** "Headroom on existing grid" is a politically distinct
   story from "we need to build a new substation" — defensible because it
   has utility and ratepayer alignment.
3. **Hardware credibility.** Nvidia + Dell + Eaton-grade design is a
   signal-rich partnership stack that legitimizes the product to
   hyperscaler buyers.

### 7.2 Moat analysis

| Asset | Defensibility | Notes |
|---|---|---|
| Pulte partnership | Medium | Pulte can deploy with others; logo-strong but contractually unknown |
| Span panel installed base | High | 5+ years of installs; real switching cost for builders already standardized on Span |
| Power-control IP and certification | High | Long process to UL-list and PUC-clear a panel with this behind-the-meter authority |
| Orchestration software | Low-medium | Pure software; replicable by any well-funded competitor |
| Hardware design | Low | Pure integration of commodity parts; no proprietary silicon |
| Tariff/regulatory relationships | Medium | Slow to build, slow to copy |
| Brand / first-mover narrative | Low | Decays as competitors enter |

The **real moat** is the *combination* of panel installed base + builder
channel + power-control IP. None of those alone is a moat; all three
together are reasonably hard to copy in under 3–4 years.

### 7.3 Strategic timing

XFRA launches into a market where interconnection queues are 5–7 years and
worsening; inference is becoming the dominant AI workload; public opposition
to centralized DCs is rising; behind-the-meter generation is having its
capital moment ($7.65B in fuel-cell deals Q4 2025–Q1 2026); and utilities
are actively exploring tariff and grid-flex programs (EPRI DCFlex, NREL,
Verrus, Emerald AI). The timing is good. If Span had launched two years
earlier, the headroom story would have landed in a less-receptive market.

Position is defensible for **3–4 years** on the unique combination of
installed base + builder channel + regulatory work. Beyond that, defensibility
depends on whether the orchestration layer becomes a meaningful product
differentiator (low confidence) or whether anchor-tenant contracts and
tariff treatments lock in distribution (medium confidence). The position is
**fragile to two things:** anchor-tenant non-renewal (if a hyperscaler walks,
economics force consolidation) and PUC reversal (if a major state rules
against residential headroom resale, the model loses its primary market).

### 7.4 Risk inventory

**Technical:**

| Risk | Severity | Likelihood |
|---|---|---|
| Glycol leak at residential site | Medium | Low |
| Cooling system failure in extreme heat (Phoenix August) | Medium | Medium |
| Orchestrator partial-failure cascade | High | Low-medium |
| GPU thermal throttling under residential cooling envelope | Medium | Medium |
| Tampering / physical-security breach | High | Low at pilot, rising at national |

**Operational:**

| Risk | Severity | Likelihood |
|---|---|---|
| Truck-roll cost balloons as fleet grows | High | High |
| Host churn (homeowner sells, divorces) | Medium | Medium |
| Internet provider non-cooperation | Low | Low |
| Recall or rolling firmware issue | High | Low |

**Market / business:**

| Risk | Severity | Likelihood |
|---|---|---|
| Hyperscaler walks from anchor contract | Critical | Low at pilot, medium at scale |
| GPU resale price compression | High | Medium-high |
| Latency premium fails to materialize | High | Medium |
| Decentralized GPU networks undercut | Medium | High but different workload |
| Channel slowdown (Pulte ramp) | Medium | Low-medium |

**Regulatory / political:**

| Risk | Severity | Likelihood |
|---|---|---|
| PUC denies favorable tariff for XFRA load | Critical | Medium |
| Ratepayer-advocate challenges model | High | Medium-high |
| HOA / local zoning ban for "data center on residential lot" | Medium | Medium |
| Federal regulation of distributed compute as critical infrastructure | Low-medium | Low |
| Tax-treatment changes | Medium | Low |

**Catastrophic / tail:**

| Risk | Severity | Likelihood |
|---|---|---|
| House fire attributed to XFRA unit | Critical | Very low |
| Mass GPU theft (organized) | High | Low at pilot, rising |
| Cybersecurity incident exposing buyer data | Critical | Low |
| Climate event taking out a regional cluster | Medium | Climate-dependent |

The **two binary risks** that dominate the thesis are PUC tariff outcomes
(existential, plausible) and truck-roll cost scaling (probable, structural).
The most over-discussed risks in press coverage are acoustic/visual
neighborhood objections (real but manageable via the HVAC form factor) and
NIMBY (which the pilot's new-construction-only design largely sidesteps).

---

## 8. Adjacent opportunities and four directional bets

### 8.1 Adjacencies Span isn't currently pursuing

Eight extensions are visible from the analysis. Listed in order of strategic
distance from XFRA's current scope:

1. **Bundled grid-services revenue.** Span has the panel, orchestration, and
   battery. Selling demand-response capacity to utilities as a separate
   revenue stream alongside compute resale is a natural extension at no
   incremental capex.
2. **Heat reuse for residential hot water.** The 12 kW IT load is rejected
   as low-grade heat. In northern climates, capturing it to pre-warm
   domestic hot water (Heata-style) could reduce a host's heating bill
   30–50% in winter and turn "free electricity" into "free electricity and
   free hot water."
3. **Sovereign / institutional channel.** The same hardware in the same
   enclosure at a school, fire station, library, or municipal building
   serves a different buyer (the institution itself) at different economics
   (host-as-customer). Sidesteps PUC risk entirely.
4. **Insurance-as-a-product.** The glycol/cooling/fire risk at residential
   addresses creates a real insurance product opportunity. At fleet scale,
   a 10–20% margin lift; as a side effect, makes the host conversation
   easier.
5. **Hardware-as-a-service to non-Span markets.** The XFRA enclosure
   (HVAC-form-factor outdoor liquid-cooled GPU pod) sold as a product to
   buyers who don't want the full service model — telcos for cell-tower
   compute, retailers, smaller builders, federal facilities.
6. **Multi-rack site upgrade path.** If one host site proves out at 19 kW,
   the same lot with a slightly larger pad can host 2–4 racks. Unlocks
   tightly-coupled workloads at sites where the host is willing — likely
   commercial, civic, or large-rural-residential.
7. **Geographic expansion to high-heating-cost markets.** The Southwest is
   easiest to *start*; the most economically interesting US market for the
   residential-headroom thesis combined with heat reuse is the
   **Northeast**, where residential rates are high but heating costs are
   higher.
8. **Federal / DOD edge inference.** The same product, contracted federally
   for on-base deployment, sidesteps the entire PUC question and likely
   fetches much higher per-node revenue. Not currently pursued.

Of these, (1) utility grid services and (6) multi-rack upgrade are nearest
to Span's current capability. (3) sovereign, (7) Northeast with heat reuse,
and (8) federal are larger strategic shifts but reuse most of the existing
investment.

### 8.2 Four directional bets: "what if it isn't Span"

If a different operator wanted to build something in the same neighborhood
as XFRA — small, distributed compute solving the speed-to-power gap — but
deliberately chose a different shape, there are four coherent archetypes
worth naming. Each is a *bet*, not a recommendation. Each one beats Span on
something specific and loses to Span on something specific.

**Bet A — "Hearth": heat reuse for the US Northeast.**
The first US Heata. Compute heats hot water in homes that currently pay
$0.30+/kWh for heat. Compute is incidental; the value is reclaimed heat.
Workload is batch / offline AI training and rendering. Channel is utility
energy-efficiency programs + insulation/HVAC installers. Hardware is
1U-class (~1 kW) on the hot-water tank. Economic model is heat-reclamation
savings for the host + compute resale. Geography: New England + NY.

*Why it works.* Northeast heating costs are genuinely expensive
($2,000–$4,000/yr per home is normal). Reclaiming that as a free byproduct
of compute is a consumer-grade pitch. Doesn't compete with Span — serves
a workload Span can't take.

*Why it might not.* Single-box compute is hard to differentiate. Utility
EE programs are slow. Batch market is small and price-pressured.

**Bet B — "Steeple": tiny DCs at cell towers and telco huts.**
Take Span's pitch and put it on infrastructure already built to host
equipment, with commercial power, fiber, security, and a tenant relationship.
Channel: tower co-owners (American Tower, Crown Castle) + WISPs in rural.
Hardware envelope: 2–4 racks per site (~40–80 kW). Workload: low-latency
inference (consumer AI, AR/VR, autonomous driving).

*Why it works.* This is exactly the parallel Cordovil pointed to in his
XFRA assessment. Towers/huts have power, security, fiber, and operators
who already do site rounds. Per-site economics are way better than
residential. No ratepayer politics.

*Why it might not.* This is the obvious move and AWS Wavelength / Verizon
5G Edge are already on it. Tower co-owners want a cut. Buyer doesn't care
where the box is if both meet latency.

**Bet C — "Civic": sovereign inference at municipal/county facilities.**
Sell a turnkey "local AI compute" box to schools, libraries, fire stations,
town halls, hospitals, regional government. The selling point isn't
speed-to-power — it's data sovereignty and local control. Hardware: 1–2
racks per site. Economic model: annual contract (host-as-customer) with
optional shared-capacity overflow.

*Why it works.* US schools and small munis can't use most AI offerings
because of data governance (COPPA, FERPA, HIPAA), IT staffing, and
political sensitivity. A local box is a real answer. Government contracts
are sticky. Nobody else is targeting this buyer directly.

*Why it might not.* Government procurement is glacially slow. School IT
budgets are small. Margin per site is low. "AI in schools" is politically
volatile.

**Bet D — "Confluence": tiny DC co-deployed with new utility-scale
solar+storage.**
Solar developers already have to build grid interconnections that are partly
underused most of the day. Co-locating a tiny DC on the parcel uses that
underutilization, gives the developer extra revenue, and gives the compute
buyer cheap renewable-tagged inference. Channel: NextEra, Invenergy, AES,
EPCs. Hardware: 2–4 racks per parcel scaling to 5–10. Geography: solar-rich
states with long interconnection queues (TX, AZ, NV, CA).

*Why it works.* Solar developers have a real problem (interconnection
queues, curtailment) compute can absorb. Buyers want renewable-tagged
inference for ESG. The compute is genuinely cheaper because it's stranded
power. No residential politics.

*Why it might not.* Solar developers are slow procurement targets. The
renewable-tagged premium may collapse as RECs and PPAs commoditize. Crusoe
is likely to move here.

**Trade-off summary.**

| Bet | Channel | Hardware | Workload | Beats Span on | Loses to Span on |
|---|---|---|---|---|---|
| **Hearth** (A) | Utility EE + HVAC installers | 1U / ~1 kW | Batch | Northeast economics; consumer-grade pitch | Per-site capacity; not competing for inference dollars |
| **Steeple** (B) | Tower co-owners + WISPs | 2–4 racks / ~40–80 kW | Low-latency inference | Per-site ops; existing power & fiber | Residential proximity for very-last-mile latency |
| **Civic** (C) | Direct gov procurement | 1–2 racks / ~20–40 kW | Sovereign inference | Sticky revenue; no PUC risk | Sales cycle; ceiling on price per site |
| **Confluence** (D) | Solar developers + EPCs | 2–4 racks scaling to 5–10 | Inference + scheduled training | Capex per MW; renewable tag | Speed to first site (depends on solar cadence) |

For Northwest Ohio specifically, **Bet D (Confluence) is the unusually
strong local fit** because of First Solar's CdTe PV supply chain at
Perrysburg and the workforce already trained for the Meta build. Bet C
(Civic) is the second-strongest fit, given the density of UToledo / BGSU
institutional buyers in the geography.

---

## 9. Watchlist and decision gates

### 9.1 What we still don't know — priority order

In order of how much each, if answered, would change the assessment:

1. **First-tenant pricing and contract terms.** Who buys, how much, for how
   long, at what price.
2. **First PUC ruling on XFRA-relevant tariff.** Likely Nevada or Arizona —
   sets precedent for high-rate states and for OH ratepayer-advocate
   posture.
3. **Per-node operating cost from the pilot.** Truck-roll frequency,
   glycol/cooling maintenance events, failure rates.
4. **Orchestrator architecture and partial-failure behavior.** Public
   technical disclosure or independent audit.
5. **Host satisfaction and churn at month 12 of the pilot.** The home-as-host
   model is novel; churn data is the leading indicator of channel scaling.
6. **Commercial XFRA spec and pricing (announced for early 2027).**
   Determines whether Span is residential-only or a broader distributed-
   compute brand.
7. **Insurance carrier underwriting position on residential compute pods.**
   The first major carrier to write or refuse coverage sets the market.
8. **Hyperscaler edge-strategy disclosures (AWS, Azure, Google).** If the
   hyperscalers commit publicly to internal edge buildouts, XFRA's
   addressable market shrinks.

### 9.2 What an investor would want before writing a check

1. **Anchor-tenant LOI.** Span has not publicly disclosed a per-node price.
   The whole valuation hinges on a hyperscaler signing wholesale terms.
   Until one does, the $210K target is derived, not market-validated.
2. **PUCO posture on distributed-compute aggregation.** AEP's >25 MW tariff
   is the arbitrage. Ratepayer advocates are already framing distributed
   compute as "hyperscalers parking load on residential ratepayers." A
   future PUCO ruling could close the door.
3. **AEP-Dayton zone-specific wholesale prices.** PJM-wide RT LMP averaged
   $51/MWh in 2025 (+47% YoY). AEP-Dayton-specific data is harder to pull;
   if it runs >$60/MWh, behind-the-meter residential-resale economics
   tighten. Flag as thin data.
4. **The $3M/MW vs. $310K-hardware gap.** Span's published *system* cost
   of $3M/MW implies $58K/node — but a 16× RTX PRO 6000 Blackwell server
   alone is $200K+ at street prices. Either the figure excludes GPUs (most
   likely — GPUs depreciate on a different cycle), or there's significant
   subsidy or financing in the mix. Worth a direct question to Span.
5. **Truck-roll cost at scale.** Ops at $7K/yr is an estimate; actual data
   from the 100-home pilot won't surface until Q3 2026.

### 9.3 Decision gates

Two explicit gates an investor should treat as binary on/off:

- **Gate 1 — Anchor tenant.** A signed multi-year hyperscaler contract at
  edge-premium pricing. Without it, the revenue side of the model is
  derived, not validated. Likely resolution window: Q4 2026 – Q2 2027.
- **Gate 2 — First major PUC ruling.** A favorable ruling on residential
  aggregation in any of NV, AZ, or OH would de-risk the model nationally;
  an adverse ruling in any high-rate state would put the model on defense.
  Likely resolution window: 2027.

A "yes" on both converts XFRA into a category-defining business with a
3–4 year structural moat. A "no" on either likely confines XFRA to a
profitable-but-bounded business in low-rate markets — a real outcome, but
not the gigawatt-scale ambition publicly framed.

---

## 10. Sources

### Span / XFRA — primary

- [SPAN — XFRA press release](https://www.span.io/blog/span-announces-xfra-a-distributed-data-center-solution-to-close-the-speed-to-power-gap-for-ai-compute-demand) (Apr 13, 2026)
- [SPAN press release via BusinessWire](https://www.businesswire.com/news/home/20260414372626/en/SPAN-Announces-XFRA-a-Distributed-Data-Center-Solution-to-Close-the-Speed-to-Power-Gap-for-AI-Compute-Demand)
- [XFRA.ai](https://www.xfra.ai/) — white-paper landing page

### Span / XFRA — secondary

- [Latitude Media — Can Span turn homes into AI inference hubs?](https://www.latitudemedia.com/news/span-to-launch-mini-ai-data-centers-for-distributed-at-home-compute/)
- [pv-magazine USA — Span and Nvidia AI data centers in your backyard](https://pv-magazine-usa.com/2026/04/15/span-and-nvidia-to-develop-ai-data-centers-in-your-backyard-lowering-electric-bills/)
- [Data Center Richness — Liquid-Cooled GPUs Come to the Backyard](https://datacenterrichness.substack.com/p/liquid-cooled-gpus-come-to-the-backyard)
- [Network World — Startup SPAN teams with Nvidia](https://www.networkworld.com/article/4170966/startup-span-teams-with-nvidia-to-put-data-center-nodes-in-your-backyard.html)
- [Technology.org — SPAN Plans Mini AI Data Centers in 80,000 Homes](https://www.technology.org/2026/05/13/span-home-ai-data-center-nodes/)
- [CNBC — Nvidia and PulteGroup are helping this startup put mini data centers on homes](https://www.cnbc.com/2026/05/05/nvidia-pulte-span-mini-data-centers-on-homes.html)
- [Fortune — Startups are installing tiny data centers in people's homes](https://fortune.com/2026/05/15/startups-tiny-data-centers-beleaguered-electrical-grid-heata-span/)
- [DataCenter Dynamics — Electrical panel company SPAN launches XFRA](https://www.datacenterdynamics.com/en/news/electrical-panel-company-span-launches-xfra-distributed-data-center-offering/)
- [mgrid.org — Span/NVIDIA XFRA targeting 1 GW by 2027](https://mgrid.org/2026/04/14/span-and-nvidia-launch-xfra-distributed-ai-data-center-network-targeting-1-gw-by-2027/)
- [Inc. — Nvidia's New Partnership Wants to Put Mini AI Data Centers on Your House](https://www.inc.com/moses-jeanfrancois/nvidia-mini-ai-data-center-house/91340588)
- [Moneywise — Nvidia and Span want to turn your home into a mini data center](https://moneywise.com/news/top-stories/nvidia-span-xfra-homes-mini-data-centers)
- [Cybernews — Mini data centers to be launched across the US](https://cybernews.com/ai-news/mini-data-center/)
- [IndexBox — Span XFRA distributed data center for AI](https://www.indexbox.io/blog/span-launches-xfra-distributed-data-center-solution-to-power-ai-growth/)

### Northwest Ohio — Meta Bowling Green and adjacent data-center activity

- [JobsOhio — Meta NW Ohio announcement](https://www.jobsohio.com/newsroom/news-press/regional-growth-partnership-and-jobsohio-welcome-meta-to-northwest-ohio-with-new-800-million-data-center-announcement)
- [Meta Data Centers — Hello Bowling Green](https://datacenters.atmeta.com/2025/04/hello-bowling-green/)
- [Toledo Blade — Meta power plant filings (Dec 2025)](https://www.toledoblade.com/local/suburbs/2025/12/15/filings-reveal-details-plant-power-meta-data-center/stories/20251212084)
- [Data Center Dynamics — Meta Toledo campus](https://www.datacenterdynamics.com/en/news/meta-to-develop-data-center-campus-outside-toledo-ohio/)
- [Toledo Free Press — Waterville hyperscale prospect](https://toledofreepress.com/hyperscale-data-center-eyed-for-waterville-township/)
- [Signature Associates — Oregon, OH 170-acre sale](https://www.signatureassociates.com/oregon-oh-planning-for-big-data-center-as-tech-companies-swarm-region/)
- [WTOL — Lucas County moratorium debate](https://www.wtol.com/article/tech/lucas-county-eyes-data-centers-next-big-opportunity-not-everyone-is-on-board/512-05498023-4191-46d2-912f-52e123b986b2)
- [Spectrum News — Meta Prometheus 1 GW (New Albany)](https://spectrumnews1.com/oh/columbus/news/2025/11/13/meta-gigawatt-data-center-new-albany-)

### Tariffs and electricity rates

- [Vorys — PUCO AEP DC tariff analysis](https://www.vorys.com/publication-public-utilities-commission-of-ohio-authorizes-tariff-for-aep-ohios-data-center-customers-requires-end-of-moratorium-on-new-services-for-data-centers)
- [AEP Ohio — Data Center Tariff page](https://www.aepohio.com/company/about/rates/data-center-tariff/)
- [Power Magazine — PUCO approval](https://www.powermag.com/regulator-approves-aep-ohios-landmark-data-center-tariff/)
- [electricityrates.com — AEP Ohio June 2025 rates](https://electricityrates.com/resources/aep-ohio-electricity-rate-increase-2025/)
- [ohenergyratings.com — Toledo Edison bill](https://www.ohenergyratings.com/resources/understanding-your-toledo-edison-bill)
- [Monitoring Analytics — PJM 2025 Q2 SOM](https://www.monitoringanalytics.com/reports/Market_Messages/Messages/2025q2-som-pjm-press-release.pdf)

### GPU pricing benchmarks

- [getdeploying — RTX PRO 6000 Blackwell](https://getdeploying.com/gpus/nvidia-rtx-pro-6000)
- [getdeploying — B200 reference](https://getdeploying.com/gpus/nvidia-b200)
- [IntuitionLabs — H100 rental prices](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)
- [Spheron — GPU cloud pricing 2026](https://www.spheron.network/blog/gpu-cloud-pricing-comparison-2026/)

### Direct peers — distributed compute in homes and small buildings

- [Heata — company and unit](https://www.heata.co/company/heata-unit)
- [DCD — Civo partners with Heata](https://www.datacenterdynamics.com/en/news/civo-partners-with-heata-to-offer-batch-processing-on-digitized-boilers/)
- [Tech.eu — Heata UK waste-heat reuse](https://tech.eu/2023/10/24/heata-is-transforming-the-uks-household-energy-costs-with-waste-heat-reuse/)
- [MIT Technology Review — UK startup reuses waste heat from cloud computing](https://www.technologyreview.com/2023/08/18/1077548/computer-waste-heat/)
- [Qarnot Computing](https://compute.qarnot.com/)
- [TechCrunch — Qarnot servers in central-heating boilers](https://techcrunch.com/2023/01/09/qarnot-creates-green-data-centers-by-putting-servers-in-central-heating-boilers/)
- [Deep Green Energy](https://deepgreen.energy/)
- [DCD — UK swimming pools heated by data centers](https://www.datacenterdynamics.com/en/news/uk-data-center-startup-offers-to-heat-britains-swimming-pools-with-waste-heat/)
- [The Next Web — Deep Green £200M Octopus deal](https://thenextweb.com/news/deep-green-octopus-energy-swimming-pools-data-centre)

### Modular / prefab data centers

- [Compass + Schneider prefab announcement](https://www.compassdatacenters.com/news/compass-and-schneider-electric-announce-prefabricated-white-space-module-to-accelerate-data-center-delivery-timelines/)
- [Vertiv — MegaMod CoolChip launch](https://www.vertiv.com/en-emea/about/news-and-events/news-releases/vertiv-launches-high-density-prefabricated-modular-data-center-solution--to-accelerate-global-deployment-of-ai-compute/)
- [IEEE Spectrum — AI-ready modular DC slashes deployment time](https://spectrum.ieee.org/modular-data-center)
- [Crusoe — Spark Factory announcement](https://www.crusoe.ai/resources/newsroom/crusoe-announces-new-manufacturing-facility-to-produce-modular-ai-factories)
- [Crusoe — Edge Zones announcement](https://www.crusoe.ai/resources/newsroom/crusoe-unveils-crusoe-edge-zones)
- [BusinessWire — Energy Vault + Crusoe Spark framework agreement](https://www.businesswire.com/news/home/20260211881549/en/Energy-Vault-and-Crusoe-Announce-Strategic-Framework-Agreement-for-Deployment-of-Crusoe-Spark-Modular-AI-Factory-Units-to-Deliver-Crusoe-Cloud)

### Edge colocation and hyperscaler / telco edge

- [EdgeConneX](https://www.edgeconnex.com/)
- [EdgePresence](https://www.edgepresence.com/edge-presence-micro-data-centers/)
- [Gartner — On-premises public cloud appliance comparison](https://www.gartner.com/en/documents/4270199)
- [Constellation Research — AI vertical integration race](https://www.constellationr.com/insights/news/google-cloud-aws-microsoft-azure-ai-vertical-integration-race)
- [Google Cloud — AI infrastructure at Next '26](https://cloud.google.com/blog/products/compute/ai-infrastructure-at-next26)
- [TechEdgeAI — Kyndryl + Google Distributed Cloud expansion](https://techedgeai.com/kyndryl-teams-with-google-cloud-to-expand-distributed-cloud-services-for-enterprise-ai-workloads/)

### Behind-the-meter generation

- [Crusoe](https://www.crusoe.ai/)
- [Crusoe — Energy-First Approach](https://www.crusoe.ai/resources/blog/welcome-to-the-era-of-byo-power)
- [Bloom Energy — Data Center Power solutions](https://www.bloomenergy.com/industries/data-center-power/)
- [DCD — Bloom Energy $5B Brookfield partnership](https://www.datacenterdynamics.com/en/news/bloom-energy-signs-5bn-partnership-with-brookfield-to-deploy-fuel-cell-tech-across-ai-data-centers/)
- [Bloom Energy Investor — 2026 Power Report](https://investor.bloomenergy.com/press-releases/press-release-details/2026/Data-Centers-Plan-to-Reduce-Reliance-on-Grid-Finds-Bloom-Energys-2026-Power-Report/default.aspx)
- [Introl — Fuel cells $7.65B dark horse](https://introl.com/blog/fuel-cells-data-center-power-dark-horse-7-billion)
- [FluxCore Data Systems](https://fluxcoredatasystems.com/blog/what-is-behind-the-meter-btm-energy-and-why-it-matters-for-ai-compute/)

### Grid-flex orchestration

- [Emerald AI + Nvidia launch](https://www.emeraldai.co/blog/launching-the-first-power-flexible-ai-factory-with-nvidia)
- [NVIDIA Blog — AI factories and grid stress](https://blogs.nvidia.com/blog/ai-factories-flexible-power-use/)
- [Axios — Nvidia, Emerald AI, energy companies on flexible DCs](https://www.axios.com/2026/03/23/utilities-nvidia-emerald-ai-data-centers)
- [DCD — Emerald AI flexible grid assets](https://www.datacenterdynamics.com/en/analysis/in-perfect-harmony-how-emerald-ai-is-turning-data-centers-into-flexible-grid-assets/)
- [Fortune — Emerald AI and Nvidia fast-pass for grid connects](https://fortune.com/2026/03/31/emerald-ai-nvidia-fast-pass-data-center-grid-connects/)
- [Introl — Data centers as grid stabilizers](https://introl.com/blog/data-centers-grid-stabilizers-flexible-power-nvidia-epri-2026)

### Decentralized GPU marketplaces

- [Securities.io — GPU rendering wars (Render vs. Akash vs. AWS)](https://www.securities.io/gpu-rendering-wars-render-akash-aws/)
- [FinanceFeeds — Top 5 decentralized GPU platforms 2026](https://financefeeds.com/top-5-decentralized-gpu-platforms-for-ai-developers-in-2026/)
- [io.net — comparison piece](https://io.net/blog/io-net-vs-akash-vs-render-network-which-decentralized-platform-actually-delivers)
- [Akash Network — AkashML](https://akash.network/blog/akashml-managed-ai-inference-on-the-decentralized-supercloud/)
- [Yellow Research — AI compute demand and crypto GPU networks](https://yellow.com/research/ai-compute-demand-crypto-gpu-networks-gap-2026)

### Northwest Ohio workforce and supply chain

- [IBEW Local 8 — jobs page](https://www.ibew8.org/)
- [IBEW national — data-center surge](https://ibew.org/electrical_worker/the-data-center-surge-a-new-generation-of-ibew-jobs/)
- [UToledo PVIC](https://www.utoledo.edu/research/pvic/)
- [UToledo — NW Ohio glass innovation hub](https://news.utoledo.edu/index.php/07_01_2024/utoledo-contributes-solar-expertise-to-new-31m-northwest-ohio-glass-innovation-hub)

### Companion documents in this repository

- [span-xfra-research-brief.md](./span-xfra-research-brief.md)
- [span-xfra-competitive-landscape.md](./span-xfra-competitive-landscape.md)
- [xfra-analysis-report.md](./xfra-analysis-report.md)
- [nw-ohio-revenue-analysis.md](./nw-ohio-revenue-analysis.md)
- [concept-doc.md](./concept-doc.md)
- [index.html](./index.html) — interactive presentation
- [span-xfra-presentation.pdf](./span-xfra-presentation.pdf)
