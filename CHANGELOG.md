```markdown
# Changelog

All notable changes to PS Toolbox will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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