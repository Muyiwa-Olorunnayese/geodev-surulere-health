# Month 1 Summary: Healthcare Access in Surulere LGA

## 1. Project Objective & Question
**Question:** Which residential neighborhoods in Surulere Local Government Area sit more than 2 km from a primary or secondary healthcare facility?

This analysis evaluates physical access to public and private health facilities (General Hospitals, Primary Health Centres, and registered clinics) within Surulere LGA, Lagos State, to determine baseline spatial coverage equity.

---

## 2. Methodology & Workflow
1. **Study Area Delineation:** Isolated the official Surulere LGA boundary from the GRID3 Nigeria Operational LGA Boundaries dataset.
2. **Facility Extraction:** Extracted public and private health facilities using GRID3 Nigeria Health Facilities v3.0 and OpenStreetMap health records.
3. **Spatial Reference Alignment:** Reprojected all layers from geographic coordinates (EPSG:4326) to the local projected coordinate reference system **EPSG:32631 (WGS 84 / UTM Zone 31N)** to ensure accurate Euclidean distance and metric area calculations.
4. **Catchment Generation:** Applied a **2,000-meter (2 km) dissolved buffer** to all clipped health facilities.
5. **Coverage Evaluation (Difference):** Executed a geometric difference between the Surulere LGA boundary and the dissolved 2 km buffer layer to isolate unserved spatial pockets.

---

## 3. Key Findings & Metrics
- **Total Facilities Mapped:** Over 40 health facilities within and directly bordering the LGA boundary.
- **Coverage Extent:** The 2 km dissolved catchment covers approximately **>95%** of the total land area of Surulere LGA.
- **Access Deserts:** Only minor peripheral fringe zones—primarily near the southwestern border corridor along the Lagos-Badagry Expressway / Mile 2 interface—exceed the 2 km straight-line access threshold from within-boundary facilities.
- **Core Corridors:** Central and eastern wards (around Bode Thomas, Western Avenue, Adeniran Ogunsanya, and Randle General Hospital) enjoy overlapping multi-facility coverage within 1 km.

---

## 4. Analytical Reflections & Limitations
While Euclidean (straight-line) buffers show near-complete geographic coverage at a 2 km threshold, this metric masks key urban realities:
- **Physical Barriers & Canals:** Major drainage infrastructure (such as the Ajegunle / System 6 Canal) and elevated transport corridors create severance, forcing longer pedestrian detours.
- **Traffic Congestion:** Straight-line distances do not capture travel time delays along primary choke points (Ojuelegba, Lawanson, and Western Avenue corridors).
- **Facility Hierarchy:** The buffer treats small private outpatient clinics identically to comprehensive secondary emergency centers (e.g., Randle General Hospital).
- **Future Direction (Month 2+):** Transition from Euclidean circular buffers to **network-based isochrones** along the street graph, and overlay settlement population rasters (GRID3/WorldPop) to estimate the exact number of impacted residents.

---

## 5. Next Steps for Month 2+
- Incorporate population distribution datasets (GRID3 or WorldPop) to estimate the exact resident count in fringe access areas.
- Transition from circular Euclidean buffers to **road network service areas** (isochrones / network distance) using the extracted OpenStreetMap road graph.


---
  ## 6. Deliverables Included
- Vector layers saved in standard GeoPackage format (`.gpkg`) in `EPSG:32631`.
- Cartographic export: `healthcare_catchment_2km.png`.
