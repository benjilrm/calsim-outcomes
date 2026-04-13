# Overview
This repository calculates demands and combines them with deliveries output from the CalSim model to generate tier outcomes

# Structure and Navigation
The 'Scripts/' folder contains all relevant code. Run scripts based on numerical order of subfolders

Scripts/ 
    
    ├── 1. Master crosswalk/
    │   └── master_crosswalk.Rmd                         # Generates master list of demand units necessary for analysis and their respective delivery IDs
    ├── 2. Tracing systems to demand units/
    │   └── system_demand_unit_tracing_loop.Rmd          # Traces each SW-reliant system back through its purchases to any demand units it is potentially served by
    ├── 3. Additional processing for ArcGIS and igraph/
    │   ├── 1. calculating_demand_by_system.Rmd          # Following Jenny's 2025 methodology, estimates drinking water demands for each system
    │   └── 2. calculating_demand_by_demand_unit.Rmd     # Takes the system-level demands and combines with the traced system --> demand unit output to estimate demands by demand unit
    ├── 4. Demand unit lat_longs/
    │   └── demand_unit_lat_longs.Rmd                    # Generates a master sheet of all SW and GW systems, and their respective demand units, including lat/longs for each demand unit
    └── 5. Tier calculations/
    │   ├── 1. calsim_outcomes_function.Rmd              # Compiles static demands with CalSim delivery outputs to calculate % demand met by year, and all tier calculations
        └── 2. summary_diagnostics.Rmd                   # Visualisations and diagnostics regarding tier calculations
