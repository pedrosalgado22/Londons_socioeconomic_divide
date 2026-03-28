# River Thames Connectivity and London's East-West Divide: A Geospatial Analysis

A geospatial analysis of how Thames crossing infrastructure shapes socioeconomic inequality across London's boroughs, identifying the relationship between river accessibility and deprivation in East London.

**Course:** Geospatial Intelligence 2025/2026 — Nova IMS, Universidade Nova de Lisboa  
**Author:** Pedro Salgado

---

## Research Question

*Is there a measurable relationship between Thames crossing accessibility and socioeconomic deprivation across London boroughs, and what does it reveal about the city's enduring east-west divide?*

---

## Repository Contents

1. `London Analysis.aprx` — ArcGIS Pro project file containing all layers, maps and analytical outputs
2. `LondonsEastWestEconDivide.pdf` — final report
3. `OnePager.pdf` — project proposal one-pager
4. `OnePager_GeoInt_Template.pdf` — Nova IMS one-pager template
5. `Presentation_and_Final_Report_GeoInt_Guidelines.pdf` — Nova IMS course guidelines
6. `Teachersannotations` — teacher's improvement suggestions

---

## Context

The River Thames has shaped London's socioeconomic characteristics for its entire existence. As the river enabled the city's rise as a global trading hub, it simultaneously created a persistent barrier to north-south connectivity, addressed very unevenly across the city's east-west axis. Today, the contrast is clearer than ever: while West London is spoiled for choices to cross the river by all modes of transportation, East London has to choose between the never-ending traffic of the Blackwall Tunnel, the expensive Dartford Crossing, or a slow and inefficient ferry. Traditional London buses in the East have also adjusted to this reality, running as few routes as possible across the river in the eastern boroughs.

The reasons for this imbalance are political, geographical and historical. Geographically, the river's conditions for building get considerably harder as it flows eastward — wider spans demanded more complex and costly engineering, delaying any Eastern bridge construction well into the twentieth century. Tower Bridge, built in 1886 as the most eastern fixed crossing at the time, required a ludicrous amount of effort, money and brute-force engineering to be built where it is, and it is still in Central-East London, showing how difficult it has historically been to push crossings further east.

Beyond geography, the economic history of London's East End was long dominated by docklands, heavy industry and working-class settlement. It was in East London that a significant share of the British Empire's ships arrived and unloaded, with the Port of London operating as the most important port in the world during the height of the Empire. As Britain's port industry and global dominance faded over the twentieth century, East London was left abandoned and stuck in time, with its working-class, industrial legacy continuing to weigh politically on the area whenever new infrastructure was being considered.

This project is aligned with **UN Sustainable Development Goal 10 — Reduced Inequalities**, specifically targets 10.1, 10.2 and 10.3, which concern income inequality, universal social and economic inclusion, and equal opportunities. Infrastructure accessibility is a fundamental enabler of inclusion, and where it is absent, inequality becomes entrenched.

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

## Key Findings

Raster distance maps, infrastructure counts and borough-level aggregation consistently pointed to the same reality throughout the analysis: East London emerged as both the most deprived region in the city and the least prepared in terms of mobility, while West London clearly outranked all other regional groupings by a wide margin.

A moderate-to-strong correlation was found between crossing count by borough and the Socioeconomic Index (R² = 0.44), rising to R² = 0.60 after excluding three genuine structural outliers whose situations cannot be accurately captured through composite indices:

- **City of London** — Europe's main financial centre, with a residential population of approximately 8,583 people and over half a million daily workers, making it effectively a reverse commuter zone whose income figures bear no resemblance to those of a standard residential borough. The City does not form part of London's 32 boroughs and operates in a largely separate manner to the rest of the city, with its own governance structure and a distinct mayor, the Lord Mayor of the City of London.
- **Kensington and Chelsea** and **Hammersmith and Fulham** — among London's most affluent boroughs, but historically resistant to large-scale infrastructure developments including bridges, major roads and cycling infrastructure, with planning decisions following very different trajectories from those observed elsewhere in the city. This explains the mismatch between high socioeconomic performance and unusually low accessibility scores for areas in or adjacent to Central London.

The continuous raster mean distance measure proved less reliable than the discrete crossing count — it did not account for borough boundaries or, most importantly, the river as a physical barrier, with boroughs near the City of London transport hotspot being disproportionately advantaged. Despite this, it still confirmed the same broader east-west pattern, with East London consistently dominating the areas furthest from a crossing.

On the future of East London: potential solutions are controversial and difficult to implement. Since the 1990s, proposals for new road crossings have faced strong opposition from local communities and environmental groups, constrained further by London City Airport's presence since 1987. Recent developments point to a more hopeful trajectory — the Silvertown Tunnel, the Elizabeth Line, and the regeneration of Canary Wharf and Greenwich have begun to reshape East London's place within the city. However, as Europe increasingly moves away from car-based mobility, non-motorised and public transport alternatives will be essential. The Thames Clippers could evolve into a genuine commuter service rather than remaining primarily a tourist attraction. Boroughs such as Newham or Barking and Dagenham could host the first high-capacity cycle highways on the eastern side of the river. Further expansion of the DLR and Underground, alongside tram reintroduction, could offer solutions better suited to East London's infrastructural constraints. As London continues to grow and approaches 10 million residents, it is crucial that renewed and targeted efforts are made to avoid leaving East London and its more vulnerable populations even further behind.

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
