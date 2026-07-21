# The Compounding Treatment Effects of Transit Network Expansion on Proximate Labor Markets: Evidence from Denver

## Overview
This project uses a staggered difference-in-differences (DiD) event study design to estimate whether Denver's phased rail network expansion (2013–2020) affected labor market outcomes in nearby Census tracts — and whether these effects compound as new lines connect to an increasingly expansive system.

## Research Question
Does expanding a public transit network improve labor market outcomes (income, employment, hours worked) in proximate areas, and do these effects grow or diminish as the network becomes more interconnected?

## Data
- **Source:** American Community Survey (ACS) 1-year estimates, 2011–2024, pulled via the `tidycensus` R package
- **Geography:** Census tracts across the Denver metro area (Denver, Arapahoe, Jefferson, Adams, Douglas counties)
- **Treatment variable:** Proximity (within 800m / ~0.5 mile) to a Denver RTD rail station, based on station opening dates
- **Treatment cohorts:** Three groups of station openings (2013 W Line; 2016–17 A/B/R Lines; 2019–20 E/F/R/G/N Lines), consolidated to allow event-study comparison across expansion phases

## Methodology
- Spatial join (via `sf`) assigning each Census tract to its nearest rail station and calculating distance
- Treatment cohort assignment based on station opening year and proximity threshold
- Staggered DiD / event study framework (in progress), with three planned control group specifications: outer geographic control, radius-based control, and propensity score matching
- Outcome variables: median household income, hours worked, unemployment rate
- Controls: age, education, racial composition, residential stability (to help distinguish labor market improvement from gentrification/compositional change)

## Status
✅ Data pull and cleaning complete

✅ Spatial join and treatment cohort assignment complete

🔄 Control group construction (propensity score matching) in progress

🔄 Event-study regression estimation not yet run

📅 Full results expected as part of senior thesis, Fall 2026

## Tools
R, `tidycensus`, `sf`, `dplyr`, `fixest`, `ggplot2`

## Files
- `Denver.Rmd` — data import, spatial join, and treatment assignment pipeline
