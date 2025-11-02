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

 ## Quick start

 ### 1) Create a Python environment (recommended: conda/mamba)

 ```bash
 # Create environment (Python 3.11 or newer recommended)
 conda create -n soildepth python=3.11 -y
 conda activate soildepth

 # Install geospatial stack from conda-forge
 conda install -c conda-forge -y \
   jupyterlab numpy pandas geopandas rasterio rioxarray shapely pyproj \
   scikit-learn scikit-gstat pykrige matplotlib seaborn tqdm gdal
 ```

 Alternative (pip-only) often works on Linux, but geospatial wheels may be tricky on macOS/Windows. Prefer conda above.

 ```bash
 pip install jupyter numpy pandas geopandas rasterio rioxarray shapely \
   scikit-learn scikit-gstat pykrige matplotlib seaborn pyproj tqdm
 ```

 ### 2) Launch notebooks

 ```bash
 # From the repository root
 jupyter lab
 ```
 Then open:
 - `codes/Spatial_data_assembly.ipynb` (prepare inputs)
 - `codes/interpolation.ipynb` (interpolate/model and map)

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

 If this work or the workflow is useful in your research or teaching, please cite relevant sources. For example:

 Peralta, N. R., et al. (2021). Mapping soil depth in southern Pampas, Argentina using ancillary data. Soil Science Society of America Journal.

 (Replace or expand with the exact citation you use in your work.)

 ## License

 No license specified. Until a license is added, all rights reserved by the authors. If you intend to share or reuse, add a `LICENSE` file (e.g., MIT, BSD-3-Clause) and update this section.

 ## Acknowledgements

 - Open-source geospatial ecosystem: `geopandas`, `rasterio`, `rioxarray`, `shapely`, `pyproj`, `scikit-learn`, `pykrige`, `scikit-gstat`, and others.
 - Course and case study context for soil depth mapping.


