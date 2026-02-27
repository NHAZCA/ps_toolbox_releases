```markdown
# Changelog

All notable changes to PS Toolbox will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.12.0] - 2026-02-27

### Added
- Add version suffix to ARPA output filenames
- Add DEM section point aggregation with distance-weighted mean velocity.
- Add velocity-mode CSV export to sections with X, velocity, and DEM elevation columns. Remove old generic CSV writer, properly close shapefile writer after processing.
- Add --changelog option to release.py for custom changelog files. When provided, reads the changelog body from a markdown file instead of auto-generating from git commits. The version header and date are added automatically.
- Add release automation script and workflow documentation. `release.py` automates post-build release: changelog generation from git commits, plugins.xml update, git tagging, and GitHub release creation with artifact uploads. Supports --dry-run preview mode.
- Add clean command to setup.py to remove Cython build artifacts. Supports; `python setup.py clean` (standalone); `python setup.py b clean` (build then clean). Removes .pyd, .c files from module directories and build/ folder.

### Fixed
- Fix Datafusion empty output when no DEM is provided.  Conditionally select model (n_unknown) based on DEM availability. With DEM use 12 parameter model (3D strain tensor). Without DEM use 6 parameter model (2D displ gradients).

### Changed
- Change DEM overlay bin size to spacing // 3 for finer resolution
- Use half DEM pixel spacing as bin size for DEM overlay with small markers and alpha
- Plot velocity PS points on DEM topographic profile. When a DEM is provided in velocity output mode, PS points are placed at their interpolated elevation on the profile line (colored by velocity) instead of on a separate twin axis. No-DEM and displacement modes unchanged.
- grep permission for claude code
- Plugin: Update ARPA glob pattern to match new filename with version suffix
- Plugin: Replace deprecated boolean QgsRubberBand geometry type with QgsWkbTypes.LineGeometry


## [0.11.99] - 2026-02-16

### Added
- Interferometric Sections: PS velocity points plotted on DEM topographic profile at interpolated elevation, colored by velocity

### Fixed
- Datafusion: Fixed empty output when no DEM is provided by conditionally selecting model based on DEM availability
- Plugin: Replaced deprecated boolean `QgsRubberBand()` geometry type with `QgsWkbTypes.LineGeometry`

### Changed
- Updater now points to GitHub releases
- Replaced deprecated `wmic` command with CIM method for hardware identification

## [0.11.98] - 2025-10-31

### Added
- New Reference Point: now handle data formatted with ARPA style
- New Reference Point: automatic update of REF_POINT column values

### Changed
- New Icons for the New Reference Point tool

## [0.11.97] - 2025-10-23

### Added
- ARPA format: Historical/Update analysis type selection
- ARPA format: Analysis version parameter (0-99)
- ARPA format: Dynamic filename generation based on analysis type
- Format: `CSM_<start>_<end>_<area>_<track><orbit><analysis><version>.shp`
- Example: `CSM_20180101_20201231_Milano_113AH0.shp`
- Orbit: A (Ascending) or D (Descending)
- Analysis: H (Historical) or U (Update)
- ARPA format: Dynamic XML metadata based on analysis type
- Comprehensive cross-repository development workflow documentation

### Changed
- Updated Format module parameter structure

### Fixed
- **License activation**: Fixed PowerShell UUID retrieval failing in compiled executables by using full PowerShell path, `shell=False`, execution policy bypass flags, and proper console window suppression for frozen apps

### Technical
- Format/core.py: Added `analysis_type` and `analysis_version` parameters
- Format/core.py: Dynamic analysis suffix in filename generation (lines 1058-1063)
- Format/core.py: Dynamic GSP_ID in XML metadata (lines 1214-1215)