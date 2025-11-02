 # Soil Depth Interpolation & Spatial Data Assembly

 This repository assembles spatial datasets and produces soil depth interpolation products for multiple fields (e.g., F05, F06, F07, F10). Workflows are implemented as Jupyter notebooks using common geospatial Python libraries.

 ## Repository layout

 - `codes/`
   - `Spatial_data_assembly.ipynb`: Loads, cleans, and harmonizes vector/raster layers (boundaries, EC, elevation, hardpan) into analysis-ready datasets.
   - `interpolation.ipynb`: Performs spatial interpolation / modeling of soil depth and generates maps/rasters.
 - `data/`
   - GeoPackages (`*.gpkg`) such as `Fxx_boundary.gpkg`, `Fxx_EC_*.gpkg`, `Fxx_elevation.gpkg`, `Fxx_hardpan.gpkg`.
   - Raster grids such as `*.grd`/`*.gri` (DEM or model outputs) used in the analysis.

 > Tip: Run notebooks from the repository root so relative paths to `data/` and `codes/` resolve correctly.

 ## Data notes

 - Field-level layers are stored as GeoPackages (`*.gpkg`) and rasters (`*.grd`/`*.gri`).
 - File name prefixes denote fields (e.g., `F05`, `F06`, `F07`, `F10`).
 - Some rasters may be large; operations can be memory-intensive. Close other apps if you encounter memory pressure.

 ## Reproducibility and paths

 - Execute notebooks from the project root so relative paths like `data/F05_boundary.gpkg` work unmodified.
 - If you relocate the repository, update any hard-coded paths inside the notebooks accordingly.

 ## Troubleshooting

 - If you see `GDAL`/`PROJ` errors, ensure you installed packages from `conda-forge` and that the active environment is the one created above.
 - On macOS with Apple Silicon, prefer `miniforge`/`mambaforge` and keep everything on `conda-forge` to avoid mixing channels.

 ## Citation

Peralta, N. R., Alesso, C. A., Costa, J. L., & Martin, N. F. (2022). Mapping soil depth in southern pampas Argentina using ancillary data and statistical learning.  Soil Science Society of America Journal, 86, 65–78.  https://doi.org/10.1002/saj2.20350


