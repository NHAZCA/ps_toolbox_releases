```markdown
# Changelog

All notable changes to PS Toolbox will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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

### Technical
- Format/core.py: Added `analysis_type` and `analysis_version` parameters
- Format/core.py: Dynamic analysis suffix in filename generation (lines 1058-1063)
- Format/core.py: Dynamic GSP_ID in XML metadata (lines 1214-1215)