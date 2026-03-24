# Lake-Ice-Cover-Monitoring-Using-Sentinel-1-SAR
## Overview

Monitoring lake ice cover is crucial for understanding climate variability, hydrological processes, and seasonal transitions in cold regions. Traditional optical satellite data often face limitations due to cloud cover and polar darkness, making Synthetic Aperture Radar (SAR) a powerful alternative.

This project presents a time-series analysis of lake ice dynamics using Sentinel-1 SAR data, focusing on Lestijärvi Lake in Finland. By leveraging radar backscatter (VV polarization), the analysis captures freeze–thaw patterns and temporal variations in lake surface conditions.

The workflow integrates Google Earth Engine (GEE) with Python-based data analysis tools to extract, process, and visualize lake-specific SAR signals over time.

## Objectives
- Extract lake boundaries using satellite-derived land cover data
- Analyze Sentinel-1 VV backscatter over the lake surface
- Monitor temporal changes in ice cover conditions
- Generate spatial and temporal visualizations of lake ice dynamics

## Study Area
- Location: Lestijärvi Lake, Finland
- A northern European lake characterized by seasonal freezing conditions
- Selected due to its clear seasonal ice formation patterns

 ## Tools & Technologies
1. Google Earth Engine (GEE) – Data access and preprocessing
2. Python – Data analysis
3. geemap – Interactive mapping and visualization
4. xee – Integration of GEE with xarray
5. xarray – Multi-dimensional data handling
6. matplotlib – Visualization

## Datasets Used
1. Sentinel-1 SAR (COPERNICUS/S1_GRD)
- VV polarization
- All-weather, day/night imaging capability
- Used to detect surface changes in lake conditions

2. Dynamic World Land Cover (GOOGLE/DYNAMICWORLD/V1)
- Used to extract lake mask
- Based on mode classification (June–September) to ensure accurate water delineation

### Figure 1: Weekly Sentinel-1 VV Backscatter Maps (2022–2023)
<img width="2852" height="3294" alt="image" src="https://github.com/user-attachments/assets/93af6952-3c55-4d2a-8618-eb3c3bb23263" />

### Figure 2: Temporal Variation of Mean VV Backscatter
<img width="555" height="449" alt="image" src="https://github.com/user-attachments/assets/6ca74e0f-874b-49d7-84da-4feb91781a6d" />

## Results Interpretation
The Sentinel-1 backscatter time series clearly captures the seasonal freeze–thaw cycle of Lestijärvi. During winter months (Dec–Feb), the lake exhibits very low backscatter values (dark blue/purple tones), indicating stable ice cover with minimal surface roughness. This is further supported by the sharp drop in VV backscatter (~ -22 to -24 dB) in the time series plot, marking peak ice thickness and extent.

As temperatures rise into spring (March–April), backscatter values increase (green–yellow tones), reflecting ice melt and increased surface heterogeneity due to water exposure and wet snow. The time series shows a corresponding rapid rise in VV values, indicating the transition from frozen to open water conditions.

During summer (May–September), the lake maintains higher backscatter values (~ -14 to -18 dB), representing ice-free open water, where wind-driven surface roughness dominates the radar response. Spatial maps during this period are more uniform, confirming stable open water conditions.

In autumn (October–November), a gradual decline in backscatter is observed, signaling the onset of refreezing, before returning to winter ice conditions.

Overall, the analysis demonstrates that Sentinel-1 VV backscatter is highly effective in tracking lake ice phenology, capturing freeze onset, peak ice cover, melt transition, and open water phases with clear temporal consistency.


## Limitations
1. Sentinel-1 spatial resolution may not capture fine-scale ice heterogeneity
2. Backscatter interpretation can be affected by:
- Wind-induced surface roughness
- Wet snow conditions
3. Dynamic World classification may introduce minor boundary inaccuracies
4. Rolling mean smoothing may reduce short-term variability (e.g., rapid freeze/thaw events)
5. Requires careful interpretation without ground validation

## Notes
1. Using summer months (June–September) for lake masking improves classification accuracy
2. Weekly aggregation helps in identifying seasonal trends more clearly
3. This workflow is scalable and can be applied to other lakes globally
4. Integration of GEE + Python enables efficient handling of large spatiotemporal datasets



Use multi-polarization SAR (VV + VH) for improved accuracy

Validate results with in-situ observations
