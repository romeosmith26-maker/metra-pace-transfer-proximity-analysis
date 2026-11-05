# Metra–Pace Transfer Proximity Analysis

ArcGIS Pro analysis of Pace bus stop proximity, route presence, and scheduled weekday service around four Metra Union Pacific West Line stations: Geneva, Wheaton, Glen Ellyn, and Elmhurst.

## Project Overview

This project evaluates how Pace bus access differs around selected Metra UP-W stations by combining spatial proximity measures with scheduled transit service data.

The analysis compares:

- Unique Pace stops within 0.25 mile of each station
- Number of Pace routes represented
- Distance to the nearest Pace stop
- Scheduled weekday trips serving stops within each station catchment

The goal was to determine whether the physical number of nearby bus stops corresponds with the amount of scheduled service available around each Metra station.

## Research Question

**How do Pace stop proximity, route presence, and scheduled weekday service differ among selected Metra UP-W stations?**

## Study Area

Four suburban Metra UP-W stations were selected for comparison:

- Geneva
- Wheaton
- Glen Ellyn
- Elmhurst

Each station was analyzed using a 0.25-mile Euclidean station catchment.

## Data Sources

- Pace bus-stop spatial data
- Pace GTFS data, August 2026 feed
  - `routes.txt`
  - `trips.txt`
  - `calendar.txt`
  - `stops.txt`
  - `stop_times.txt`
- Metra station data
- Metra rail-line data
- Esri Light Gray basemap

## Methodology

1. Created 0.25-mile Euclidean catchments around the four selected Metra stations.
2. Identified Pace stops within each catchment.
3. Deduplicated physical stop locations and summarized stop counts and route presence.
4. Used nearest-feature analysis to calculate the distance from each Metra station to the nearest Pace stop.
5. Integrated Pace GTFS routes, trips, calendar, stops, and stop-times tables.
6. Filtered GTFS records to weekday service.
7. Matched scheduled trips to GTFS stops located within each station catchment.
8. Counted each unique trip ID once per station catchment, even when the same trip served multiple stops inside that catchment.

## Results

| Station | Stops | Routes | Nearest Stop | Weekday Trips |
|---|---:|---:|---:|---:|
| Wheaton | 15 | 3 | 139 ft | 80 |
| Elmhurst | 10 | 2 | 101 ft | 68 |
| Geneva | 4 | 2 | 234 ft | 42 |
| Glen Ellyn | 13 | 1 | 91 ft | 27 |

## Key Findings

- **Stop density did not directly reflect scheduled service.** Geneva had only 4 nearby stops but 42 scheduled weekday trips, while Glen Ellyn had 13 nearby stops but only 27 trips.
- **Wheaton had the broadest service footprint** among the four stations, with the greatest route diversity and highest scheduled weekday trip count.
- **Physical proximity varied independently of service level.** Glen Ellyn had the closest Pace stop at approximately 91 feet, while Geneva had the greatest nearest-stop distance at approximately 234 feet.

## Planning Implication

Station-area transit access should not be evaluated by stop count alone. Scheduled service and route diversity provide important additional context when assessing the usefulness of Metra–Pace connections.

## Limitations

This is a screening-level proximity and scheduled-service analysis.

The 0.25-mile catchments use straight-line Euclidean distance and therefore do not account for:

- Actual pedestrian-network walking distance
- Railroad crossings or other physical barriers
- Transfer wait times
- Metra–Pace timetable coordination
- Passenger ridership or actual transfer activity

Scheduled weekday trip counts describe service available at stops within each catchment and should not be interpreted as direct measures of transfer quality.

## Skills Demonstrated

- ArcGIS Pro
- Spatial joins
- Buffer analysis
- Stop deduplication
- Nearest-feature analysis
- GTFS data processing
- Relational joins
- Attribute filtering
- Transit-service analysis
- Cartographic layout and comparative mapping

## Project Maps

### Station Proximity Maps

![Metra–Pace station maps](Metra+Pace%20Connectivity%20Page%201.png)

### Results & Implications

![Metra–Pace results](Pace+Connectivity%20Page%202.png)
## Future Improvements

Potential extensions include:

- Pedestrian-network service areas instead of Euclidean buffers
- Morning and evening peak-period service analysis
- Direct comparison of Pace departure times with Metra arrivals
- Transfer-wait-time analysis
- Expansion to additional Metra stations or corridors

## Author

Romeo Smith  
Northern Illinois University  
Earth, Atmosphere and Environment — Geospatial Systems
