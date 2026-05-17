# Northwest Ohio XFRA — per-node revenue analysis

*Investor-grade back-of-envelope · prepared 2026-05-17*

---

## Bottom line

Gross revenue lands in a **$170K–$280K per node per year** band. Base case **~$210K/node/yr**.

Against a NW Ohio cost floor of **~$82K** (residential power here is *cheaper* than NV/AZ), gross margin runs **40–70%** per node. That's structurally the best of any geography modeled in the deck.

---

## Why NW Ohio matters — three things the research confirms

### 1. Demand has already arrived — Meta is confirmed

**Meta announced $800M / 350 MW in Middleton Township, Wood County (just north of Bowling Green, ~20 miles south of Toledo), April 2025.** Ground broken 2025, online 2027. Not a rumor — JobsOhio + Meta direct.

- 715,000 sq ft on 280 acres off SR-582 / Dixie Hwy
- Dedicated 350 MW gas plant being built by Will-Power (Wood County), fast-tracked through the Ohio Power Siting Board with no public hearings
- ~100 permanent jobs; >1,000 construction at peak
- Meta's 24th US data center, 28th globally; AI-optimized

Plus three other live prospects in the same footprint:

- **Oregon, OH (Lucas County):** 170 acres sold Nov 2024 for $17.3M, up to 8 buildings planned
- **Waterville Township (Lucas County):** developer eyeing 1,000–1,400 acres; township imposed a 12-month moratorium Dec 17, 2025
- **Lucas County:** Commissioner Pete Gerken proposed a 90–120 day countywide pause in Dec 2025

**Signal:** Demand for compute capacity in this footprint is no longer theoretical. The politics around hyperscale-scale builds are already hostile — which is structurally favorable for distributed / residential models that bypass the hyperscale-site permitting fight.

Sources: [JobsOhio announcement](https://www.jobsohio.com/newsroom/news-press/regional-growth-partnership-and-jobsohio-welcome-meta-to-northwest-ohio-with-new-800-million-data-center-announcement) · [Meta Bowling Green page](https://datacenters.atmeta.com/2025/04/hello-bowling-green/) · [Toledo Blade — power plant filings](https://www.toledoblade.com/local/suburbs/2025/12/15/filings-reveal-details-plant-power-meta-data-center/stories/20251212084) · [DCD — Meta Toledo campus](https://www.datacenterdynamics.com/en/news/meta-to-develop-data-center-campus-outside-toledo-ohio/) · [Toledo Free Press — Waterville](https://toledofreepress.com/hyperscale-data-center-eyed-for-waterville-township/)

### 2. The AEP Ohio Data Center Tariff is an arbitrage door

PUCO approved AEP Ohio's data-center tariff July 9, 2025; effective July 23, 2025. It applies only to new loads **>25 MW aggregate** and requires:

- **85% take-or-pay** of subscribed capacity for up to 12 years, regardless of actual usage
- 4-year maximum load ramp
- 8-year minimum contract term
- 3-year minimum-charge exit fee

XFRA nodes are individually ~19 kW — three orders of magnitude below the 25 MW threshold. They get billed on residential tariffs.

**This is the single strongest defensible NW Ohio thesis point.** In the same regulatory geography, two compute footprints face wildly different cost structures: a hyperscaler pays for 85% of capacity for 12 years regardless of utilization; an aggregator of XFRA nodes pays only for energy actually used.

Sources: [PUCO/Vorys analysis](https://www.vorys.com/publication-public-utilities-commission-of-ohio-authorizes-tariff-for-aep-ohios-data-center-customers-requires-end-of-moratorium-on-new-services-for-data-centers) · [AEP DC tariff page](https://www.aepohio.com/company/about/rates/data-center-tariff/) · [Power Magazine](https://www.powermag.com/regulator-approves-aep-ohios-landmark-data-center-tariff/)

### 3. Power here is actually cheap

- **AEP Ohio residential:** 9.94 ¢/kWh (Jun 2025 – Aug 2026)
- **Toledo Edison residential:** ~9.5–9.8 ¢/kWh

Both are *below* the NV/AZ $0.13/kWh the deck assumes for the Southwest pilot. Per-node power cost moves from $17.5K in NV/AZ to **~$13K in NW Ohio** — a $4.5K margin pickup before any other factor.

Sources: [electricityrates.com — AEP Ohio 2025](https://electricityrates.com/resources/aep-ohio-electricity-rate-increase-2025/) · [ohenergyratings.com — Toledo Edison](https://www.ohenergyratings.com/resources/understanding-your-toledo-edison-bill)

---

## The revenue number — three independent back-solves converge

The XFRA node is **16x NVIDIA RTX PRO 6000 Blackwell** (96 GB, server tier).

### Method A — Retail GPU pricing, discounted to wholesale

Median retail rent for RTX PRO 6000 Blackwell: **$2.25–$3.56/GPU-hr** as of May 2026 ([getdeploying.com](https://getdeploying.com/gpus/nvidia-rtx-pro-6000)). Span sells wholesale to hyperscalers, not retail to GPU renters — apply standard wholesale-to-retail discount of **60–70%** of retail. Inference utilization typically lands **80–90%** (vs 60–70% for training).

| Scenario | $/GPU-hr | Utilization | Wholesale ratio | Annual/node |
|---|---|---|---|---|
| Bear | $2.00 | 70% | 0.55 | $108K |
| Base | $2.50 | 85% | 0.65 | **$193K** |
| Bull | $3.00 | 90% | 0.70 | $264K |

Formula: $/GPU-hr × 16 GPUs × 8,760 hrs × utilization × wholesale ratio

### Method B — Congruent Ventures asset-value back-solve

Yokell (Congruent Ventures) framed each XFRA node as **~$1M of asset value** — derived from NVIDIA's $50B capex/GW × 1 GW ÷ 50,000 nodes. At typical data-center asset yield (15–25% gross revenue / asset value), that lands at **$150K–$250K/yr**.

Source: [mgrid.org — Span/NVIDIA XFRA launch](https://mgrid.org/2026/04/14/span-and-nvidia-launch-xfra-distributed-ai-data-center-network-targeting-1-gw-by-2027/)

### Method C — Span's own framing

Span CEO: revenue "exceeds the cost of the XFRA system itself" (no specific number disclosed). Span publicly quotes **$3M/MW for XFRA vs $15M/MW for traditional data centers**. At 19.2 kW/node, $3M/MW implies *system* capex ~$58K. If revenue exceeds system cost on a yearly basis, that's a hard floor — and Methods A and B both land well above it.

Source: [Latitude Media — Span mini AI data centers](https://www.latitudemedia.com/news/span-to-launch-mini-ai-data-centers-for-distributed-at-home-compute/)

### Three methods converge at $180K–$230K

Base-case revenue assumption: **$210K per node per year.**

---

## NW Ohio per-node P&L (annual)

| Line | **NW Ohio** | NV/AZ (deck) | CA (deck) | Source |
|---|---|---|---|---|
| Power | **$13K** | $17.5K | $41K | AEP residential 9.94 ¢/kWh × 134,500 kWh |
| Internet | $1K | $1K | $1K | $80/mo gigabit fiber |
| Ops | $7K | $7.5K | $8K | Truck rolls, monitoring, insurance |
| Capex amort (5yr) | $61K | $61K | $61K | $310K hardware ÷ 5 yr |
| **Cost floor** | **~$82K** | $87K | $111K | |
| Target revenue (base) | $210K | $200K | $200K | derived |
| **Gross margin** | **$128K (61%)** | $113K (57%) | $89K (45%) | |

**NW Ohio is structurally the strongest market in this comparison.**

---

## Scenario range

| Scenario | What it assumes | Revenue/node | NW Ohio margin |
|---|---|---|---|
| **Bear** | No edge premium; wholesale-only; 70% utilization | $170K | ~$88K |
| **Base** | Mild edge premium (1.2x); 85% util; standard wholesale | $210K | ~$128K |
| **Bull** | Edge premium materializes (1.5x); 90% util; PUCO blesses residential aggregation | $280K | ~$198K |

For a regional pilot of even **1,000 nodes**, base-case gross revenue is **~$210M/yr** with **~$128M/yr** in regional gross margin before Span corporate overhead and any local revenue share.

---

## What I'd want before writing a check

1. **Anchor-tenant LOI.** Span has not publicly disclosed a per-node price. The whole valuation hinges on a hyperscaler signing wholesale terms. Until one does, the $210K target is a derived number, not a market-validated one.

2. **PUCO posture on distributed compute aggregation.** AEP's >25 MW tariff is the arbitrage. Ratepayer advocates are already framing distributed compute as "hyperscalers parking their load on residential ratepayers." A future PUCO ruling on residential aggregation could close the door. The Brattle "Untapped Grid" framing is Span's pre-emptive defense.

3. **AEP-Dayton zone-specific wholesale prices.** PJM-wide RT LMP averaged **$51/MWh in 2025** (+47% YoY). AEP-Dayton specific is harder to pin without a direct PJM portal pull — if AEP-Dayton runs >$60/MWh, behind-the-meter residential-resale economics tighten. Flag as thin data.

4. **The $3M/MW vs $310K-hardware gap.** Span's published *system* cost of $3M/MW implies $58K/node total — but a 16x RTX PRO 6000 Blackwell server alone is $200K+ at street prices. Either the $3M figure excludes GPUs (most likely — GPUs depreciate on a different cycle), or there's significant subsidy or financing in the mix. Worth a direct question to Span.

5. **Truck-roll cost at scale.** Ops at $7K/yr is an estimate. Actual data from Span's 100-home pilot (Pulte/Southwest) won't be visible until Q3 2026.

---

## The investor framing for NW Ohio

This isn't a story about whether XFRA economics work — it's a story about whether **NW Ohio captures any of the value if they do**.

Meta is already building 350 MW in Wood County. That's confirmed hyperscale-tier compute demand in this exact footprint. The question for the region is whether the distributed-compute layer emerging *alongside* the hyperscale layer gets sited here too.

**The numbers say it should:**

- Lower residential power than NV/AZ
- The widest hyperscale-tariff arbitrage in any major data-center geography (AEP >25 MW take-or-pay)
- First Solar's CdTe PV supply chain on-site at Perrysburg
- A workforce already getting absorbed by the Meta build (IBEW Local 8 reports JIW calls going unfilled daily)
- UToledo PVIC and BGSU College of Engineering and Innovation as technical-validation partners

The roadshow ask reduces to a single number: **$210K/node base × 1,000 nodes = $210M/yr regional gross revenue.** Even discounted to the bear case ($170K × 1,000 = $170M), the order of magnitude clears the cost of running the six meetings.

---

## Sources

### Meta Bowling Green + NW Ohio data center activity

- [JobsOhio — Meta NW Ohio announcement](https://www.jobsohio.com/newsroom/news-press/regional-growth-partnership-and-jobsohio-welcome-meta-to-northwest-ohio-with-new-800-million-data-center-announcement)
- [Meta Data Centers — Hello Bowling Green](https://datacenters.atmeta.com/2025/04/hello-bowling-green/)
- [Toledo Blade — Meta power plant filings (Dec 2025)](https://www.toledoblade.com/local/suburbs/2025/12/15/filings-reveal-details-plant-power-meta-data-center/stories/20251212084)
- [Data Center Dynamics — Meta Toledo campus](https://www.datacenterdynamics.com/en/news/meta-to-develop-data-center-campus-outside-toledo-ohio/)
- [Toledo Free Press — Waterville hyperscale prospect](https://toledofreepress.com/hyperscale-data-center-eyed-for-waterville-township/)
- [Signature Associates — Oregon, OH 170-acre sale](https://www.signatureassociates.com/oregon-oh-planning-for-big-data-center-as-tech-companies-swarm-region/)
- [WTOL — Lucas County moratorium debate](https://www.wtol.com/article/tech/lucas-county-eyes-data-centers-next-big-opportunity-not-everyone-is-on-board/512-05498023-4191-46d2-912f-52e123b986b2)
- [Spectrum News — Meta Prometheus 1 GW](https://spectrumnews1.com/oh/columbus/news/2025/11/13/meta-gigawatt-data-center-new-albany-)

### Tariffs + electricity rates

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

### Span XFRA economics

- [Span — XFRA announcement](https://www.span.io/blog/span-announces-xfra-a-distributed-data-center-solution-to-close-the-speed-to-power-gap-for-ai-compute-demand)
- [mgrid.org — Span/NVIDIA XFRA 1 GW target](https://mgrid.org/2026/04/14/span-and-nvidia-launch-xfra-distributed-ai-data-center-network-targeting-1-gw-by-2027/)
- [Latitude Media — Span mini AI data centers](https://www.latitudemedia.com/news/span-to-launch-mini-ai-data-centers-for-distributed-at-home-compute/)
- [Fortune — tiny data centers](https://fortune.com/2026/05/15/startups-tiny-data-centers-beleaguered-electrical-grid-heata-span/)

### NW Ohio workforce + supply chain

- [IBEW Local 8 — jobs page](https://www.ibew8.org/)
- [IBEW national — data center surge](https://ibew.org/electrical_worker/the-data-center-surge-a-new-generation-of-ibew-jobs/)
- [UToledo PVIC](https://www.utoledo.edu/research/pvic/)
- [UToledo — NW Ohio glass innovation hub](https://news.utoledo.edu/index.php/07_01_2024/utoledo-contributes-solar-expertise-to-new-31m-northwest-ohio-glass-innovation-hub)
