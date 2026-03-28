# River Thames Connectivity and London's East-West Divide: A Geospatial Analysis

A geospatial analysis of how the Thames River and crossing infrastructure shapes socioeconomic inequality across London's boroughs, identifying the relationship between river accessibility and deprivation in East London.

**Course:** Geospatial Intelligence 2025/2026 — Nova IMS, Universidade Nova de Lisboa  
**Author:** Pedro Salgado

<img width="2362" height="1594" alt="Image" src="https://github.com/user-attachments/assets/be7b3130-4ff3-49db-98c0-9a0626df43a4" />

---

## Research Question

*Is there a measurable relationship between Thames crossing accessibility and socioeconomic deprivation across London boroughs, and what does it reveal about the city's enduring east-west divide?*

---

## Repository Contents

1. `London Analysis.aprx` — ArcGIS Pro project file containing all layers, maps and analytical outputs
2. `LondonsEastWestEconDivide.pdf` — final report
3. `OnePager.pdf` — project proposal one-pager
4. `OnePager_GeoInt_Template.pdf` — one-pager guidelines
5. `Presentation_and_Final_Report_GeoInt_Guidelines.pdf` — project guidelines
6. `Teachersannotations` — teacher's improvement suggestions

---

## Context

The River Thames has shaped London's socioeconomic characteristics for its entire existence. As the river enabled the city's rise as a global trading hub, it simultaneously created a persistent barrier to north-south connectivity, addressed very unevenly across the city's east-west axis. Today, the contrast is clearer than ever: while West London is spoiled for choices to cross the river by all modes of transportation, East London has to choose between congested tunnels, expensive toll crossings, or a slow and inefficient ferry.
The reasons for this imbalance are political, geographical and historical. Geographically, the river's conditions for building get considerably harder as it flows eastward, as wider spans demanded more complex and costly engineering, delaying eastern bridge construction well into the twentieth century. Beyond geography, the East End's long history of docklands, heavy industry and working-class settlement left it abandoned and stuck in time as Britain's port industry declined, with its industrial legacy continuing to weigh politically on the area whenever new infrastructure was being considered.


<img width="4782" height="3381" alt="Image" src="https://github.com/user-attachments/assets/3f13ac8a-1623-416e-971b-f989dfdce534" />

---



This project is aligned with **UN Sustainable Development Goal 10 — Reduced Inequalities**, specifically targets 10.1, 10.2 and 10.3, which concern income inequality, universal social and economic inclusion, and equal opportunities. Infrastructure accessibility is a fundamental enabler of inclusion, and where it is absent, inequality becomes entrenched.

---

![Image](https://github.com/user-attachments/assets/905a1aa6-128f-4842-b38d-4d4a2fdf17cd)

---


## Data

All datasets are official open-source geospatial and socioeconomic sources. Socioeconomic variables correspond to 2019 for temporal consistency across indicators.

| Dataset | Source | Purpose |
|---|---|---|
| OS Open Rivers | Ordnance Survey | River Thames geometry and corridor delineation |
| GeoFabrik London | GeoFabrik / OpenStreetMap | Roads, rail, crossings, cycling and pedestrian networks |
| TfL Open Data | Transport for London | Public transport infrastructure, bus stops, tube and pier locations |
| Greater London boundary & boroughs | London Datastore / GLA | Administrative boundaries for the study area |
| Index of Multiple Deprivation (IMD) | GOV.UK / MHCLG | Borough-level deprivation indicator |
| Average income by borough | London Datastore / HMRC | Income indicator by place of residence |
| Education, Skills & Training (EST) | GOV.UK | Social vulnerability and human capital indicator |

---

## Methodology

1. **Data Collection** — official open-source geospatial and socioeconomic datasets from OS, TfL, GeoFabrik, London Datastore and GOV.UK
2. **Data Preprocessing** — river isolation via select-by-attribute, buffering to delineate the Thames corridor, and intersection with the Greater London boundary
3. **Infrastructure Mapping** — extraction of all river crossings and proximate public transport stops, retaining only stops within 50 metres of the Thames buffer that serve crossings directly or across their routes
4. **Raster Analysis** — continuous distance surfaces measuring how far every point in London is from a crossing or a river crossing public transport stop
5. **Spatial Analysis** — borough-level aggregation of crossing counts (discrete) and mean distances derived from raster outputs (continuous) as complementary accessibility measures
6. **Socioeconomic Integration** — construction of a composite Socioeconomic Index (SEI) from income, IMD and EST, correlated against both accessibility measures

Full methodological detail and the methodological diagram are in [`LondonsEastWestEconDivide.pdf`](./LondonsEastWestEconDivide.pdf).

---

## Results

Raster distance maps, infrastructure counts and borough-level aggregation consistently pointed to the same reality: East London emerged as both the most deprived region in the city and the least served in terms of river crossing infrastructure, while West London clearly outranked all other regional groupings by a wide margin.

A moderate-to-strong correlation was found between crossing count by borough and the Socioeconomic Index (R² = 0.44), rising to R² = 0.60 after controlling for boroughs whose structural characteristics composite indices cannot accurately capture. The continuous raster mean distance measure proved less reliable than the discrete crossing count, failing to account for borough boundaries and the river as a physical barrier, though it still confirmed the same broader east-west pattern.
On the future of East London: potential solutions are controversial and difficult to implement, with road crossing proposals facing consistent opposition since the 1990s. Recent developments are more hopeful — the Silvertown Tunnel, the Elizabeth Line and the regeneration of Canary Wharf and Greenwich have begun to reshape East London's place within the city. As Europe moves away from car-based mobility, non-motorised and public transport alternatives become essential: Thames Clippers evolving into a genuine commuter service, cycle highways in boroughs like Newham and Barking and Dagenham, and further DLR and Underground expansion. As London approaches 10 million residents, targeted efforts to close this gap are not optional.



<img width="4782" height="3381" alt="Image" src="https://github.com/user-attachments/assets/a37de36e-86e6-41a0-957d-fd939df143d9" />

---

## Tech Stack

| Tool | Purpose |
|---|---|
| ArcGIS Pro | Core geospatial analysis and cartographic output |
| ArcGIS Raster Analysis | Continuous distance surface generation |
| ArcGIS Network Analysis | Routing and accessibility assessment |
| ArcGIS Spatial Analysis | Select-by-location, intersection, buffering, spatial joins |
| Microsoft Excel | Socioeconomic data preparation and SEI construction |
| OpenStreetMap / GeoFabrik | Open geospatial data source and extraction |
| Claude Sonnet 4.6 / Opus 4.6 (Anthropic) | Research and writing assistance |

---

## Report

Full methodology, results, discussion and conclusions are in [`LondonsEastWestEconDivide.pdf`](./LondonsEastWestEconDivide.pdf).

---

*Nova IMS — Universidade Nova de Lisboa | Geospatial Intelligence 2025/2026*
