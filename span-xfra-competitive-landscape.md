---
title: "Span XFRA — Competitive Landscape and Alternate Solutions"
subtitle: "Companion brief to span-xfra-research-brief.md"
date: 2026-05-16
prepared_for: Michael Vanderpool
status: Draft v1
---

# Span XFRA — Competitive Landscape and Alternate Solutions

## TL;DR

There is **no other company in the U.S. putting a 16-Blackwell-GPU pod on the side of a single-family home**. In that exact niche, Span has the field to itself today. But XFRA is one answer to a much larger problem — *AI compute is bottlenecked by power and time-to-power, not by silicon* — and there are at least **eight other categories of solution** chasing the same gap. They differ on where the compute lives, who pays for the power, what kind of workload they target, and how they get around the grid.

The competitive picture clusters into five layers:

1. **Direct peers — distributed compute in residential / small commercial buildings.** Heata (UK), Qarnot (France), Deep Green (UK). All three are smaller, older, and operate on a *heat-reuse* thesis rather than Span's *spare-electrical-capacity* thesis. None of them are doing high-end GPU inference at Span's scale.
2. **Modular / prefab data centers.** Schneider + Compass, Vertiv MegaMod CoolChip, Crusoe Spark, Duos Edge. Cuts deployment from years to months, but still wants its own parcel and interconnection.
3. **Hyperscaler & telco edge boxes.** AWS Outposts, Azure Stack Edge, Google Distributed Cloud Edge, Verizon/AT&T 5G edge. Mature distribution channel, ridden on the telco footprint analyst Cordovil specifically held up as the *more instructive parallel* to Span.
4. **Behind-the-meter generation + DC.** Crusoe (flared gas, then Stargate-scale renewables), Bloom Energy + Brookfield, FluxCore. Solves the power problem by bringing the generator to the data center instead of the load to spare capacity.
5. **Grid-flex orchestration ("virtual capacity").** Emerald AI + Nvidia, Verrus (Sidewalk Infrastructure). Doesn't deploy any new compute — it makes existing AI factories ramp up and down in seconds to unlock grid interconnections.
6. **Decentralized GPU marketplaces.** io.net, Akash, Render, Aethir. Software-only distribution layer over already-installed consumer/prosumer GPUs. Cheap, fragmented, mostly batch.

**Strategic read:** Span is closest to telco edge in shape (small distributed compute pods) and closest to behind-the-meter generation in motivation (sidestep interconnection queues), but is *uniquely* the only one using residential headroom as the "found" capacity source. That's a thin, defensible moat *if* the regulatory and ratepayer-fairness story holds — and a fragile one if it doesn't. Heat-reuse competitors are not direct threats; they're complementary plays for a different workload (batch, not low-latency inference).

---

## 1. Direct peers — distributed compute in homes and small buildings

The closest analogs to XFRA. All three predate Span's announcement by years, but all three target *batch* or *general* workloads with a *heat-reuse* economic justification, not premium AI inference with a power-headroom justification.

### Heata (UK)

The startup most often paired with Span in 2026 press coverage. A Heata "unit" is a **compute server roughly 36×28 cm bolted to a domestic hot-water cylinder**, using a patented thermal-transfer mechanism to dump waste heat into the tank. Each unit delivers up to ~4.25 kWh of hot water per day and is rated to save the host up to **£340/year** off their heating bill, plus an estimated 1 tonne CO₂/yr. Installation takes ~2 hours; the unit raises the home's EPC rating by 4–8 points (a real-money benefit under 2026 UK rental rules).

Heata sells compute to **cloud customers via Civo** (announced 2024) and has worked with **British Gas** on a heat-reuse trial. Workloads are *offline batch* — anything latency-sensitive doesn't fit, because residential broadband and a single 1U-class box can't do it.

*Comparison to XFRA:* Heata is roughly **two orders of magnitude smaller per node** (~1 kW vs. 19.2 kW), heat-out rather than electricity-headroom, batch rather than inference, UK rather than US, no Nvidia/Dell/hyperscaler-grade hardware. They are solving a different problem in an adjacent shape.

### Qarnot Computing (France)

Founded 2010. Started by putting CPU servers inside electric *radiators* used by construction companies for new builds — the original "digital heater" thesis. Has since moved to **liquid-cooled servers feeding district heating loops or building hot water**, reusing ~95% of generated heat. Customers include major French banks, 3D animation studios, and research labs. Raised ~$55M to date.

Qarnot is the spiritual ancestor of the entire "compute as a heat source" movement. It is *not* a serious threat to XFRA: French scale, CPU/HPC focus, district-heating model that needs a host building with a hydronic loop.

### Deep Green (UK)

Heats UK leisure centres' swimming pools using **immersion-cooled HPC tubs** installed at the pool. A typical install is **~28 kW** of compute; Deep Green pays for the electricity and gives the heat to the pool free. The host pool reportedly cuts gas use ~62% and saves ~£20K/yr. Backed by a **£200M investment from Octopus Energy** to roll out to 100–150 pools.

Closer to XFRA on a few axes (immersion liquid cooling, mid-kW per site, dual-purpose energy), but it's a B2B-to-leisure-centre play in the UK, not a residential one in the US. Workloads are general cloud, not premium AI inference.

---

## 2. Modular / prefab data centers — the "speed-to-power" middle ground

If you can't put GPUs on a house but you still want to compress 3–5 years of greenfield buildout, you put them in a factory-built box and ship it. This is now an established category with multiple credible vendors and a market valued at **~$29–33B in 2025**.

### Schneider Electric + Compass Datacenters

Joint **prefabricated EcoStruxure Pod** for "white space" fit-out. First units deployed at a Compass campus in fall 2025. Schneider claims **~30% shorter deployment** (16 weeks of on-site work vs. ~36 for traditional builds) and estimates the prefab pod model can let operators **start earning revenue ~3 months sooner**.

### Vertiv MegaMod CoolChip

Vertiv's high-density, **liquid-cooled** prefabricated modular DC, explicitly positioned for AI. Vertiv claims it **halves delivery time** versus a traditional build by manufacturing and testing modules offsite.

### Crusoe Spark / Crusoe Edge Zones

Crusoe's modular AI factory, designed to scale from **hundreds of kW to hundreds of MW**, deployable as a standalone hub or grouped into clusters. Time-to-power is claimed at **as little as 3 months per unit**. Air-cooled today; **liquid-cooled version in H2 2026**. Pairs with diverse on-site power: solar, repurposed EV batteries, grid, natural gas, even small modular nuclear (SMRs). New **"Spark Factory" in Brighton, Colorado** opened to mass-produce these units; first factory-produced modules due Q3 2026. Energy Vault is signed for up to 25 MW of Spark deployments; Redwood Materials expanded from 4 to 24 Spark units (~7× original density).

### Duos Edge AI

Self-contained **55 ft × 12.5 ft modular compute pods** designed primarily for truck transport. Targeting edge AI inference in places without traditional DC infrastructure.

*Comparison to XFRA:* These are the *same workloads* (inference, sometimes training) at a *very different unit size* (100 kW to 100 MW per box, sited on commercial parcels). They compete with Span on *time-to-power* but not on *power source* — they still need a real interconnection. They're better for buyers who want a contiguous cluster; XFRA is better when you want compute distributed across many low-latency points.

---

## 3. Edge colocation — the existing carrier-grade footprint

A pre-existing real-estate play that has been quietly distributing colocation racks into metro markets for over a decade.

### EdgeConneX

Pure-play edge DC operator across North America, Europe, and APAC, focused on regional/metro markets and carrier-neutral connectivity. Announced **€500M for 12 new European edge sites** in late 2024.

### EdgePresence

Distributed edge DC infrastructure as IaaS, with multi-tenant colocation aimed at low-latency content, gaming, cloud services, and telecom. Raised **$50M in 2024** to expand into rural and urban edge environments.

*Comparison to XFRA:* These exist already, are operated by people who know how to run racks, and benefit from telco interconnection. Their unit economics on small-GPU-count sites are easier to model than Span's. The downside is they're not co-located with the *power source*, they're co-located with the *user* — they still buy commercial power on the standard interconnection queue.

---

## 4. Hyperscaler & telco edge boxes — the incumbent answer

Every big cloud already ships an edge appliance. They are not residential, they are not new, and their unit economics for the inference workloads XFRA targets are reasonably well understood.

### AWS Outposts / Snow family

Rack-format AWS infrastructure shipped into customer premises. As of April 2026, Outposts mindshare has actually **declined** (9.3%, down from 15.4% YoY) — a signal the appliance model is losing traction against hyperscaler edge zones and regional DCs.

### Microsoft Azure Stack Edge / Stack Hub

Microsoft's hybrid edge appliance. Mindshare also down (14.6% from 28.9% YoY) — similar dynamic. Azure Arc is the broader multi-cloud control plane.

### Google Distributed Cloud Edge

The Anthos-/Vertex-AI-flavored version. Recent **Kyndryl partnership** to extend the offering with managed services and Gemini integration.

### Verizon 5G Edge, AT&T edge, AWS Wavelength

Edge zones planted in telco facilities. The analyst Dell'Oro's Alex Cordovil flagged in his XFRA assessment: *"how telcos are positioning their existing footprint for AI inference at the edge — they already have power, connectivity, security and a distributed node structure, but still wrestle with running compute across a small number of GPUs per site."*

*Comparison to XFRA:* Telco edge is the most credible *structural* competitor — same distributed shape, but with carrier-grade physical security, existing fiber, and an established power interconnect. Span's bet is that the residential channel (via Pulte) lets it scale faster than telcos historically have, *and* gets latency closer to residential consumers than central offices do.

---

## 5. Behind-the-meter generation + data center — bring the power to the compute

If the bottleneck is interconnection, skip the interconnection. Generate on-site.

### Crusoe Energy

Started by burning flared methane at oilfields to mine bitcoin; pivoted to AI infrastructure around stranded and renewable energy. Operates the **1.2 GW Stargate campus in Abilene, TX** (first buildings energized within a year of breaking ground) and the new Crusoe Spark modular factory in Colorado. Named one of Fast Company's 2026 Most Innovative.

### Bloom Energy

Solid-oxide fuel cells installed behind the meter to bypass interconnection queues. Signed a **$5B deployment partnership with Brookfield** to put SOFC capacity across AI factories worldwide. Bloom is **doubling annual manufacturing capacity from 1 GW to 2 GW by end-2026**. Q1 2026 revenue **$751M, up 130% YoY**. The behind-the-meter category as a whole closed **$7.65B in binding deals from late 2025 to early 2026**.

Bloom's own 2026 Power Report: **32% of US data centers plan to operate fully off-grid on SOFC by 2030** — up from 22% six months earlier.

### FluxCore Data Systems

Builds modular data centers directly powered by on-site generation, converting "localized power generation into immediately usable compute." A nicely literal example of the behind-the-meter category.

*Comparison to XFRA:* Different philosophy — XFRA finds *existing* spare power on the residential grid; behind-the-meter players bring *new* generation to the site. They actually complement each other in many markets: at low MW, XFRA wins on speed; at high MW, BTM generation + Crusoe Spark wins on density.

---

## 6. Grid-flex orchestration — virtual capacity instead of new capacity

A different shape of solution: don't deploy new compute, make existing AI factories *behave like* flexible loads so utilities give them faster interconnection.

### Emerald AI + Nvidia

NVIDIA-backed startup with an **"Emerald Conductor"** software platform that ramps AI workloads in response to grid signals. Demonstrated in Phoenix via EPRI's DCFlex program: ramped down in 15 minutes, sustained a **25% power reduction for 3 hours**, then ramped back to baseline. Combined with **Nvidia's DSX Flex** (GPU-level telemetry at second granularity), Emerald + Nvidia claim the approach unlocks **up to 100 GW of new US grid capacity** without building any new plants.

### Verrus

Spinout from Alphabet's Sidewalk Infrastructure Partners. Testing at NREL's 70 MW data center; claims to **shift 100% of a DC's power demand from grid to on-site resources within one minute** of a utility request.

*Comparison to XFRA:* Adjacent but not directly competing. Both Span and Emerald are pitching the same political story — grid utilization is the cheap unlock — from different angles. Emerald rides on top of existing big AI factories; Span builds new tiny ones on residential headroom. A hyperscaler could plausibly use both.

---

## 7. Decentralized GPU marketplaces — the software-only "alternate"

If the question is "how do we get more AI compute online faster," the software-only answer is "stop building new boxes and aggregate the GPUs that already exist."

### io.net

Aggregates underused GPUs (consumer and enterprise) into a network it markets as "practically limitless." Claims cost reductions **up to 90%** versus hyperscalers. Published A100-equivalent cluster pricing of **$1.50–$3.50/GPU-hour** (a 15–63% discount on AWS-comparable configurations).

### Akash Network

Decentralized general-purpose compute marketplace (CPU, GPU, storage). Launched **AkashML** to provide managed AI inference on its decentralized supercloud.

### Render Network

Began as a decentralized rendering platform for 3D artists; expanded into general AI compute. Has **600+ open-weight models** on its AI Compute Subnet.

### Aethir, Fluence, others

A long tail of similar networks. Collectively, the decentralized GPU sector handled an estimated **$200M in annualized protocol revenue in early 2026**.

*Comparison to XFRA:* Different product, same thesis. XFRA distributes *new* enterprise hardware to many small sites; decentralized networks distribute *existing* heterogeneous hardware via a marketplace. Decentralized GPU networks lose on SLA, latency consistency, and security but win on cost-per-GPU-hour. They do not threaten Span on hyperscaler-grade inference — they threaten Span on the price-sensitive long tail.

---

## 8. Side-by-side comparison

| Player | Category | Where compute sits | Per-site power | Hardware target | Workload | Speed-to-power vs. greenfield | Status |
|---|---|---|---|---|---|---|---|
| **Span XFRA** | Distributed residential | Side yard of new-construction homes | ~19.2 kW | 16× RTX PRO 6000 Blackwell + 4× EPYC | AI inference, cloud gaming | 6× faster, 1/5 cost | 100-home pilot Q3 2026; >1 GW/yr target 2027 |
| Heata | Heat-reuse residential | On the host's hot-water cylinder | ~1 kW | Single-box compute (CPU class) | Offline batch cloud | n/a — heat-reuse model | UK deployments via Civo, British Gas |
| Qarnot | Heat-reuse residential & building | Inside electric radiators / district-heat loops | ~kW-class per unit | CPU/HPC | HPC, batch, rendering | n/a | Operating since 2010, ~$55M raised |
| Deep Green | Heat-reuse leisure | Inside immersion tubs at swimming pools | ~28 kW per site | HPC immersion | General cloud / HPC | n/a | UK rollout to 100–150 pools; £200M Octopus |
| Schneider + Compass | Modular prefab | Commercial parcel, Compass campus | 1–10 MW per pod | Customer-chosen | Hyperscale | ~30% faster; ~3 months sooner revenue | First units fall 2025 |
| Vertiv MegaMod CoolChip | Modular prefab | Customer commercial site | Multi-MW per module | Liquid-cooled GPU rack | AI training & inference | ~50% faster | Shipping |
| Crusoe Spark | Modular prefab + on-site power | Crusoe Edge Zones / customer site | 100s kW – 100s MW | Air today, liquid H2 2026 | AI training & inference | ~3 months per unit | Spark Factory live; 24-unit Redwood expansion |
| Duos Edge AI | Modular prefab | Anywhere a truck can deliver | Pod-scale | Customer-chosen | Edge AI inference | weeks | Shipping |
| EdgeConneX | Edge colocation | Metro markets globally | Per-rack to multi-MW | Tenant hardware | Mixed | n/a (existing facilities) | €500M Euro expansion 2024 |
| EdgePresence | Edge colocation | Rural + urban edge | Per-rack | Tenant hardware | Content, gaming, telecom | n/a | $50M expansion 2024 |
| AWS Outposts | Hyperscaler edge box | Customer premises rack | Rack-class | AWS-curated | AWS workloads | n/a | Mature, mindshare declining |
| Azure Stack Edge | Hyperscaler edge box | Customer premises | Rack-class | Microsoft-curated | Azure workloads | n/a | Mature, mindshare declining |
| Google Distributed Cloud Edge | Hyperscaler edge | Customer / partner site | Variable | GCP-curated incl. TPU 8i | Vertex/Gemini inference | n/a | Growing via Kyndryl deal |
| Telco 5G edge (Verizon/AT&T) | Telco edge | Central offices, towers | Site-class | Variable | Inference, MEC | n/a | Operational |
| Crusoe (BTM gen + DC) | Behind-the-meter | Co-located with stranded/renewable gen | 100s MW (Stargate: 1.2 GW) | Nvidia AI infra | Training + inference | Compressed (Stargate energized in ~1 yr) | Operating |
| Bloom Energy + Brookfield | Behind-the-meter generation | Anywhere SOFC fits | Multi-MW per install | Customer DC | Powers any DC | Bypasses 5–7yr queues | $5B deal; 2 GW/yr manufacturing |
| FluxCore | Behind-the-meter modular DC | Co-located with generation | Modular MW | Customer-chosen | AI | Months | Active |
| Emerald AI + Nvidia | Grid-flex orchestration | Existing AI factories | Software only | n/a — orchestrates existing GPUs | Any | Unlocks queue, no new build | Demonstrated in Phoenix via EPRI |
| Verrus | Grid-flex orchestration | Existing DCs | Software + on-site batteries | n/a | Any | Shifts 100% of load in ≤1 min | Testing at NREL 70 MW |
| io.net | Decentralized GPU marketplace | Wherever GPUs already exist | n/a | Heterogeneous existing GPUs | AI/ML, batch | Software-only | $1.50–3.50/GPU-hr; in market |
| Akash Network | Decentralized GPU marketplace | Wherever GPUs already exist | n/a | Heterogeneous | General + ML | Software-only | AkashML inference launched |
| Render Network | Decentralized GPU marketplace | Wherever GPUs already exist | n/a | Heterogeneous | Rendering + AI inference | Software-only | 600+ models on AI subnet |

---

## 9. Strategic read — where Span actually wins, and where it doesn't

**Span wins on:**
- *Speed to incremental compute capacity in a specific metro.* Six months to stand up the equivalent of a 100 MW DC, with no interconnection queue, *if* the homebuilder pipeline and tariff conversations cooperate.
- *Latency proximity to consumers.* For consumer-facing inference (AI chat, gaming, on-device assistants), being one residential hop from the end user is a real advantage that telco edge can match but modular prefab cannot.
- *Capex per MW.* Roughly $3M/MW vs. ~$15M/MW greenfield — the most quotable number from the launch.
- *Political story.* "We're using grid headroom that's already there" is a cleaner story to a PUC than "we're building a 200 MW campus with a new substation."

**Span loses (or is at parity with adversary) on:**
- *Cluster topology for frontier training.* Modular prefab, behind-the-meter Crusoe, and big telco edge sites all beat XFRA when the workload is *tightly-coupled* training. Span concedes this and positions XFRA as inference-only.
- *Per-GPU-hour cost.* Decentralized GPU marketplaces (io.net, Akash, Render) beat enterprise-grade pricing by 60–90% for any workload that can tolerate heterogeneity and weaker SLA.
- *Operability and service economics.* A truck-roll to one rack on a residential side yard is far more expensive per incident than a tech walking between racks in an EdgeConneX metro site or a Crusoe Spark cluster.
- *Existing power & physical-security trust.* Telco edge sites and behind-the-meter generation have decades of carrier-grade operating practice. A residential pad does not.
- *Capacity ceiling.* At ~30–40% household suitability (Davies, Utah State), Span's plausible US ceiling is single-digit GW. Modular + behind-the-meter solutions don't share that ceiling.

**Most direct structural threats, ranked:**
1. **Telco edge (Verizon, AT&T, AWS Wavelength).** Same distributed shape, existing fiber + power + security, and the analyst cited in Span's own coverage as the more instructive parallel.
2. **Crusoe Spark + Edge Zones.** Closest "factory-built tiny DC" product, with deployable power options and three-month time-to-power. Sites on commercial parcels rather than residences, which sidesteps Span's regulatory risk.
3. **Behind-the-meter + Emerald AI orchestration combo.** A hyperscaler that pairs Bloom SOFC with Emerald's grid-flex software gets *most* of Span's speed-to-power benefit without the residential channel friction.
4. **Modular prefab (Schneider+Compass, Vertiv).** Cuts greenfield to ~16 weeks. Doesn't compete on residential proximity but does compete on the "how fast can a hyperscaler stand up new MWs" axis.
5. **Heata / Qarnot / Deep Green.** Not strategic threats. Different workload, different geography, different physics. They are a useful *cohort* in any "tiny data center" market-map slide but not a competitive constraint.
6. **Decentralized GPU networks.** Cost ceiling, not a strategic threat. They compete for the price-sensitive long-tail of AI workloads that Span explicitly isn't pursuing.

---

## 10. Implications for a "Tiny Data Center Concept" project

A few things worth pulling forward into your own thinking:

1. **The category is now visibly real.** Modular DC, edge boxes, behind-the-meter generation, and now residential micro-nodes are no longer separate niches — they're variants on a single answer to "AI compute is power-limited." Any pitch for a tiny-DC concept benefits from naming where it sits in that taxonomy rather than treating it as novel.
2. **Channel partner is the differentiator.** Crusoe wins on flared-gas access plus the Stargate hyperscaler relationship; Span wins on PulteGroup; Heata wins on British Gas + Civo; Emerald wins on Nvidia. Hardware specs are easier to match than distribution.
3. **The grid-utilization political story is doing a lot of work.** Span, Emerald AI, and Verrus are all selling variations of "you already have the capacity, you just need to manage it better." Any new entrant needs to pick a side of the political story (or stay below it).
4. **Behind-the-meter is the closest thing to a "no, just build power" answer.** Bloom's $5B Brookfield deal and Crusoe's 1.2 GW Stargate energized in ~1 year suggest the market is willing to pay full freight to skip the queue. A tiny-DC concept that competes on speed without addressing why a buyer wouldn't just buy BTM fuel cells needs an answer.
5. **The heat-reuse axis is mostly empty in the US.** Heata, Qarnot, Deep Green all exist in Europe. No US player has executed the heat-reuse pitch at scale. If "tiny data center" includes useful heat as a byproduct, that's white space.

---

## 11. Sources

Direct peers
- [Heata — company / unit pages](https://www.heata.co/company/heata-unit)
- [DCD — Civo partners with Heata to offer batch processing on digitized boilers](https://www.datacenterdynamics.com/en/news/civo-partners-with-heata-to-offer-batch-processing-on-digitized-boilers/)
- [Tech.eu — Heata is transforming the UK's household energy costs with waste heat reuse](https://tech.eu/2023/10/24/heata-is-transforming-the-uks-household-energy-costs-with-waste-heat-reuse/)
- [MIT Technology Review — UK startup engineered a clever way to reuse waste heat from cloud computing](https://www.technologyreview.com/2023/08/18/1077548/computer-waste-heat/)
- [Qarnot Computing](https://compute.qarnot.com/)
- [TechCrunch — Qarnot creates green data centers by putting servers in central heating boilers](https://techcrunch.com/2023/01/09/qarnot-creates-green-data-centers-by-putting-servers-in-central-heating-boilers/)
- [Deep Green Energy](https://deepgreen.energy/)
- [DCD — UK data center startup offers to heat Britain's swimming pools with waste heat](https://www.datacenterdynamics.com/en/news/uk-data-center-startup-offers-to-heat-britains-swimming-pools-with-waste-heat/)
- [The Next Web — Deep Green bags £200M to heat 'hundreds' of swimming pools](https://thenextweb.com/news/deep-green-octopus-energy-swimming-pools-data-centre)

Modular / prefab
- [Compass + Schneider — Prefabricated White Space Module announcement](https://www.compassdatacenters.com/news/compass-and-schneider-electric-announce-prefabricated-white-space-module-to-accelerate-data-center-delivery-timelines/)
- [Vertiv — MegaMod CoolChip launch](https://www.vertiv.com/en-emea/about/news-and-events/news-releases/vertiv-launches-high-density-prefabricated-modular-data-center-solution--to-accelerate-global-deployment-of-ai-compute/)
- [IEEE Spectrum — AI-Ready Modular Data Center Slashes Deployment Time](https://spectrum.ieee.org/modular-data-center)
- [Crusoe — Spark Factory announcement](https://www.crusoe.ai/resources/newsroom/crusoe-announces-new-manufacturing-facility-to-produce-modular-ai-factories)
- [Crusoe — Edge Zones announcement](https://www.crusoe.ai/resources/newsroom/crusoe-unveils-crusoe-edge-zones)
- [BusinessWire — Energy Vault + Crusoe Spark Strategic Framework Agreement](https://www.businesswire.com/news/home/20260211881549/en/Energy-Vault-and-Crusoe-Announce-Strategic-Framework-Agreement-for-Deployment-of-Crusoe-Spark-Modular-AI-Factory-Units-to-Deliver-Crusoe-Cloud)

Edge colocation
- [EdgeConneX](https://www.edgeconnex.com/)
- [EdgePresence](https://www.edgepresence.com/edge-presence-micro-data-centers/)

Hyperscaler edge
- [Gartner — Comparing on-premises public cloud appliances (AWS Outposts, Azure Stack Hub, Google Distributed Cloud Edge)](https://www.gartner.com/en/documents/4270199)
- [Constellation Research — Google Cloud, AWS, Microsoft Azure: The AI vertical integration race](https://www.constellationr.com/insights/news/google-cloud-aws-microsoft-azure-ai-vertical-integration-race)
- [Google Cloud — AI infrastructure at Next '26](https://cloud.google.com/blog/products/compute/ai-infrastructure-at-next26)
- [TechEdgeAI — Kyndryl + Google Cloud Distributed Cloud expansion](https://techedgeai.com/kyndryl-teams-with-google-cloud-to-expand-distributed-cloud-services-for-enterprise-ai-workloads/)

Behind-the-meter generation
- [Crusoe — company](https://www.crusoe.ai/)
- [Crusoe — Energy-First Approach blog](https://www.crusoe.ai/resources/blog/welcome-to-the-era-of-byo-power)
- [Bloom Energy — Data Center Power solutions](https://www.bloomenergy.com/industries/data-center-power/)
- [DCD — Bloom Energy $5bn partnership with Brookfield](https://www.datacenterdynamics.com/en/news/bloom-energy-signs-5bn-partnership-with-brookfield-to-deploy-fuel-cell-tech-across-ai-data-centers/)
- [Bloom Energy Investor — 2026 Power Report press release](https://investor.bloomenergy.com/press-releases/press-release-details/2026/Data-Centers-Plan-to-Reduce-Reliance-on-Grid-Finds-Bloom-Energys-2026-Power-Report/default.aspx)
- [Introl — Fuel cells $7.65B dark horse](https://introl.com/blog/fuel-cells-data-center-power-dark-horse-7-billion)
- [FluxCore Data Systems — Behind-the-meter blog](https://fluxcoredatasystems.com/blog/what-is-behind-the-meter-btm-energy-and-why-it-matters-for-ai-compute/)

Grid-flex orchestration
- [Emerald AI — Launching the first power-flexible AI factory with Nvidia](https://www.emeraldai.co/blog/launching-the-first-power-flexible-ai-factory-with-nvidia)
- [NVIDIA Blog — How AI Factories Can Help Relieve Grid Stress](https://blogs.nvidia.com/blog/ai-factories-flexible-power-use/)
- [Axios — Nvidia, Emerald AI team with energy companies on flexible data centers](https://www.axios.com/2026/03/23/utilities-nvidia-emerald-ai-data-centers)
- [DCD — In perfect harmony: how Emerald AI is turning data centers into flexible grid assets](https://www.datacenterdynamics.com/en/analysis/in-perfect-harmony-how-emerald-ai-is-turning-data-centers-into-flexible-grid-assets/)
- [Fortune — Emerald AI and Nvidia aim to offer a fast pass for data center grid connects](https://fortune.com/2026/03/31/emerald-ai-nvidia-fast-pass-data-center-grid-connects/)
- [Introl — Data Centers as Grid Stabilizers](https://introl.com/blog/data-centers-grid-stabilizers-flexible-power-nvidia-epri-2026)

Decentralized GPU networks
- [Securities.io — GPU Rendering Wars: Render vs. Akash vs. AWS (2026)](https://www.securities.io/gpu-rendering-wars-render-akash-aws/)
- [FinanceFeeds — Top 5 Decentralized GPU Platforms for AI Developers in 2026](https://financefeeds.com/top-5-decentralized-gpu-platforms-for-ai-developers-in-2026/)
- [io.net blog — io.net vs Akash vs Render](https://io.net/blog/io-net-vs-akash-vs-render-network-which-decentralized-platform-actually-delivers)
- [Akash Network — AkashML managed AI inference](https://akash.network/blog/akashml-managed-ai-inference-on-the-decentralized-supercloud/)
- [Yellow Research — AI Compute Demand vs. Supply, Crypto Networks Stepping In](https://yellow.com/research/ai-compute-demand-crypto-gpu-networks-gap-2026)

Span (for cross-reference; full citations in span-xfra-research-brief.md)
- [SPAN — XFRA press release](https://www.span.io/blog/span-announces-xfra-a-distributed-data-center-solution-to-close-the-speed-to-power-gap-for-ai-compute-demand)
- [Latitude Media — Can Span turn homes into AI inference hubs?](https://www.latitudemedia.com/news/span-to-launch-mini-ai-data-centers-for-distributed-at-home-compute/)
- [Network World — SPAN teams with Nvidia to put data center nodes in your backyard](https://www.networkworld.com/article/4170966/startup-span-teams-with-nvidia-to-put-data-center-nodes-in-your-backyard.html)
