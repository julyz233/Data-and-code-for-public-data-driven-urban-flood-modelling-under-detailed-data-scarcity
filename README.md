# Journal of Hydrology reproducibility package

This package supports the revised manuscript on public-data-driven urban flood modelling under detailed-data scarcity.
It was generated from the local project workspace on 2026-08-10 16:43:46.

## Scope

The package is intended for editorial/reviewer reproducibility checks rather than as a complete redistribution of all raw public source data. Raw public DEM, land-cover, OpenStreetMap, and Sentinel-1 products are not duplicated here when they are available from original providers or governed by platform terms. Their exact sources, versions, and acquisition/event dates are documented in the manuscript and in `metadata/`.

The package contains the derived inputs, configurations, model outputs, evidence tables, summary tables, and scripts used to support the revised manuscript:

- processed 5 m hydraulic surfaces and UHSM rasters/masks;
- generalized synthetic drainage networks at coarse, medium, and fine densities;
- rainfall hyetographs used in the retained Xiaozhai and Zhengzhou simulations;
- retained M0-M3 model inputs and configurations for Xiaozhai and retained M1-M3 model inputs and configurations for Zhengzhou;
- selected model outputs required to audit maximum-depth fields, inundation extent, metrics, and water-balance closure;
- public-evidence and DDSC assessment tables;
- manuscript figure/table source CSV files and generated figure files;
- Python scripts used for UHSM construction, synthetic-network generation, M0-M3 simulation, DDSC assessment, figure generation, and water-balance checks.

## Directory map

| Directory | Contents |
|---|---|
| `metadata/` | Data catalogues, public-data preparation summaries, parameter tables, and QC metadata. |
| `inputs/processed_hydraulic_surfaces/` | 5 m UHSM rasters, masks, routing DEMs, depression storage, infiltration, roughness, and land-use parameter tables. |
| `inputs/synthetic_networks/` | Generalized drainage-network CSV/GPKG/QC outputs for coarse, medium, and fine settings. |
| `inputs/rainfall_inputs/` | Rainfall hyetographs for Xiaozhai R30 and the Zhengzhou 2021-07-20 event. |
| `inputs/model_inputs/` | Retained model input folders for the manuscript comparisons. |
| `inputs/model_configs/` | YAML configuration files copied from retained runs. Some original configs contain local absolute paths; use the package file map to update paths if rerunning elsewhere. |
| `inputs/evidence/` | Public-evidence inventory, candidate-screening, reviewed-evidence, and Sentinel-1/DDSC support tables. |
| `results/model_outputs/` | Selected retained model outputs, including `max_depth`, `peak_instant_depth`, `inundation_extent`, `metrics.csv`, and `mass_balance.csv`. Long time-series and hourly snapshot arrays are intentionally excluded to keep the package suitable for review upload. |
| `results/manuscript_tables/` | CSV files underlying the revised manuscript figures and tables. |
| `results/manuscript_figures/` | Revised manuscript figure exports, excluding oversized TIFF files. |
| `results/revision_capacity_control/` | Capacity-control, outfall-density, water-balance, and reviewer-response summary files. |
| `scripts/` | Source scripts required for model/input generation, simulation, DDSC assessment, plotting, and revision diagnostics. |

## Suggested reviewer checks

1. Inspect `PACKAGE_MANIFEST.csv` and `checksums_sha256.txt` to verify the file inventory.
2. Check `results/manuscript_tables/results_global_mass_balance_residuals.csv` and the retained-run `mass_balance.csv` files under `results/model_outputs/`.
3. Check the M3 drainage partition using `results/revision_capacity_control/xiaozhai_outfall_density_summary.csv`, `results/revision_capacity_control/xiaozhai_capacity_control_summary.csv`, and `results/revision_capacity_control/zhengzhou_capacity_control_summary.csv`.
4. Inspect generalized-network inputs in `inputs/synthetic_networks/*/medium/` and the outfall-controlled M3 model inputs in `inputs/model_inputs/*/M3_*`.
5. Inspect public-evidence and DDSC tables in `inputs/evidence/` and `results/ddsc_assessment/`.

## Rerun notes

The copied YAML files preserve the original run settings. Some YAML path fields were generated in the local Windows workspace and may contain local absolute paths. To rerun outside this machine, replace path entries with the corresponding package-relative files. The key scripts are:

- `scripts/build_uhsm.py`
- `scripts/build_generalized_sewer.py`
- `scripts/run_control_model_comparison.py`
- `scripts/run_revision_m2_capacity_control.py`
- `scripts/run_revision_capacity_sensitivity.py`
- `scripts/run_zhengzhou720_event_replay.py`
- `scripts/run_ddsc_credibility_assessment.py`
- `scripts/plot_results_4_*.py`

## Excluded files

The package excludes large raw public data downloads, raw simulation `timeseries.csv` files, hourly snapshot arrays, and oversized TIFF figure exports. These exclusions are documented in `EXCLUDED_FILES.md` and do not affect the manuscript-level table/figure audit.

## Repository/DOI placeholder

This local package can be uploaded to a journal supplementary-data system, Zenodo, Figshare, OSF, or a GitHub release. After institutional screening of shareable derived data, replace the placeholder in the manuscript Data Availability statement with the resulting repository URL or DOI.
