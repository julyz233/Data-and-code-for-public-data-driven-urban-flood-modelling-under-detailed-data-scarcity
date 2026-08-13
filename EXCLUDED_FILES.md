# Excluded files

The following file classes are intentionally not included:

- raw public DEM, land-cover, OpenStreetMap, and Sentinel-1 products that can be retrieved from original providers;
- full model `timeseries.csv` files, which can be hundreds of MB per run and are not needed to verify manuscript tables;
- hourly `snapshots/*.npy` arrays, because retained max-depth and peak-depth arrays are included instead;
- oversized TIFF figure exports, because PNG/PDF/SVG figure versions are included;
- temporary Word-rendering QA folders and manuscript editing helper outputs.

These exclusions keep the review package compact while preserving the inputs and outputs needed to audit the retained configurations, mass balances, and manuscript figures.
