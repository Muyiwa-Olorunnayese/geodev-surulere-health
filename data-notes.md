# Data Notes: Primary Healthcare Accessibility in Surulere LGA

## 1. GRID3 Nigeria Operational LGA Boundaries
- **Source & Link:** [GRID3 Data Hub](https://data.grid3.org/datasets/GRID3::grid3-nga-operational-lga-boundaries)
- **Version & Date:** v2.0 / v3.0 Operational Boundaries
- **Downloaded On:** 12th September 2026
- **Format:** GeoPackage (.gpkg)
- **Feature Count:** 774 national features (filtered to 1 feature: Surulere LGA)
- **Geometry Type:** Polygon / MultiPolygon
- **Key Columns:** `lga_name` (Surulere), `state_name` (Lagos), `lga_code` (25018)
- **CRS:** EPSG:4326 (WGS 84 geographic)
- **Quality & Gaps:** No missing values or nulls in administrative attributes. The boundary cleanly isolates Surulere LGA and aligns with official Lagos State administrative demarcations.

---

## 2. GRID3 Nigeria Health Facilities v3.0
- **Source & Link:** [GRID3 Data Hub](https://data.grid3.org/datasets/GRID3::grid3-nga-health-facilities-v3-0)
- **Version & Date:** v3.0
- **Downloaded On:** 12th September 2026
- **Format:** GeoPackage (.gpkg)
- **Feature Count:**  28 features within Surulere extent
- **Geometry Type:** Point
- **CRS:** EPSG:4326 (WGS 84 geographic)
- **Quality & Gaps:**
  - **Completeness:** Captures the major public facilities (Randle General Hospital, primary health centres) and larger private clinics. Minor neighborhood patent medicine stores and private outpatient clinics are not fully represented.
  - **Attribute Accuracy:** `facility_type` contains mixed categories (e.g., Primary Health Centre, Health Post, General Hospital). Some entries have nulls in `ownership` or `functional_status`.
  - **Positional Accuracy:** Facilities align closely with built-up areas on satellite imagery, though a few points fall directly along the boundary edge with Mushin and Mainland LGAs.

---

## 3. OpenStreetMap Road Network (via QuickOSM)
- **Source & Link:** [OpenStreetMap](https://www.openstreetmap.org) via QuickOSM plugin
- **Extraction Query:** `highway=*` within Surulere study area extent
- **Extracted On:** September 2026
- **Format:** GeoPackage (.gpkg)
- **Geometry Type:** LineString / MultiLineString
- **CRS:** EPSG:4326 (WGS 84 geographic)
- **Quality & Gaps:**
  - **Completeness:** Excellent street-level coverage across core Surulere avenues (Bode Thomas, Ogunlana Drive, Lawanson, Western Avenue).
  - **Attribute Accuracy:** Most minor residential roads have null values in the `surface` and `maxspeed` attributes, so roads cannot be reliably segmented by pavement quality without ground verification.
  - **Positional Accuracy:** Road alignments match satellite imagery with no visible systematic shift.


## Quality Summary & Verdict
- **Good Enough For:** Establishing baseline 2 km spatial access buffers around primary and secondary health providers in Surulere.
- **Limitations:** Straight-line distances do not account for canal barriers or traffic congestion along primary transport corridors.
