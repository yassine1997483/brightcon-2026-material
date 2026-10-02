# Does a heat pump always cut carbon? — ASHP LCA for Morocco

Open, reproducible **cradle-to-grave LCA of a residential air-source heat pump (ASHP)**
on carbon-intensive grids, built with **Brightway2 + ecoinvent 3.12 + Python**.

Case study: Morocco. The grid carbon intensity is imported **live from ecoinvent**
(no hardcoded value), the heat-pump footprint is computed across **six LCIA
categories**, and the result is benchmarked against a condensing gas boiler.

**Headline result:** on Morocco's low-voltage grid (~1107 g CO2-eq/kWh) the ASHP
delivers heat at ~424 g CO2-eq/kWh — about 73% above the gas-boiler benchmark.
The same device is a clear win on a clean grid (e.g. Norway) — *a heat pump is
only as clean as the electricity that powers it.*

## Contents

| File | What it is |
|------|------------|
| `ashp_multi_impact_ecoinvent.py` | Strict demo: imports the 6 LCIA methods + country CIs from ecoinvent via Brightway2 (no fallback), scores the multi-impact grid table. **Requires ecoinvent.** |
| `ashp_lca_ecoinvent_presentation.py` | Same engine with a documented low-voltage fallback, so it runs **without** the licensed database. Prints the headline results. |
| `environment-ashp-morocco.yml` | Conda/mamba environment for the JupyterHub kernel. |
| `slides.pdf` | Presentation slides (optional). |

## Run

```bash
# with ecoinvent available in a Brightway project:
python ashp_multi_impact_ecoinvent.py

# anywhere (uses documented low-voltage fallback if Brightway/ecoinvent is absent):
python ashp_lca_ecoinvent_presentation.py
```

Set the project and database names at the top of the scripts
(`HVAC_LCA_Morocco_Yassine` / `ecoinvent_3.12_cutoff`) to match your setup.

## Author

Yassine El Ouakour — Green Energy Park (UM6P / IRESEN),
University Mohammed VI Polytechnic, Morocco.
