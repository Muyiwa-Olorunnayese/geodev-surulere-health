# Project Brief: Primary Healthcare Accessibility in Surulere LGA

## 1. The Question
Which residential neighborhoods in Surulere Local Government Area sit more than 2 km from a primary or secondary healthcare facility?

## 2. Why It Matters
Surulere is an urban local government area in Lagos State with high population density and critical transport arteries. Evaluating physical access to public and private health facilities (such as Randle General Hospital, Gbaja and surrounding primary health centers) ensures healthcare planners can identify spatial access gaps and transit chokepoints affecting maternal and emergency care delivery.

## 3. The Data I Need
- Surulere LGA Boundary
- Health Facility Locations (Primary Health Centres, Clinics, General Hospitals)
- Major and Minor Road Network (for future travel-time routing)

## 4. Where Each Dataset Comes From
- Surulere LGA Boundary: GRID3 Nigeria Operational LGA Boundaries — https://data.grid3.org/datasets/GRID3::grid3-nga-operational-lga-boundaries — GeoPackage
- Health Facilities: GRID3 Nigeria Health Facilities v3.0 — https://data.grid3.org/datasets/GRID3::grid3-nga-health-facilities-v3-0 — GeoPackage
- Road Network: OpenStreetMap via QuickOSM (key: `highway`) — https://www.openstreetmap.org — GeoPackage

## 5. What I Will Build
A spatial catchment analysis pipeline measuring the coverage of primary and secondary healthcare providers using standard Euclidean buffers, evolving in later months into a road network-based travel time model and interactive web dashboard.
