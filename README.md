# PS Toolbox - Releases

Public releases for **PS Toolbox**, a Persistent Scatterers (PS) data post-processing application for InSAR
(Interferometric Synthetic Aperture Radar) analysis.

## Downloads

Download the latest version from the [Releases page](https://github.com/NHAZCA/ps_toolbox_releases/releases).

### Available Components

Each release includes:

1. **PSToolbox-IRIDE.zip** - QGIS Plugin
   - GUI interface for QGIS
   - Parameter configuration tools
   - Processing workflow integration

2. **src_win.zip** - Core Processing Engine (Windows)
   - Standalone executable
   - Command-line interface
   - All processing modules

3. **src_ubu.zip** - Core Processing Engine (Ubuntu/Linux)
   - Standalone executable
   - Command-line interface
   - All processing modules

## Installation

### Windows

1. Open QGIS
2. Go to **Plugins > Manage and Install Plugins > Settings**
3. Add a new plugin repository with the URL:
   ```
   https://raw.githubusercontent.com/NHAZCA/ps_toolbox_releases/main/plugins.xml
   ```
4. Search for **PSToolbox-IRIDE** in the plugin list and install it
5. Open the plugin from the toolbar and use **Download Software** to download the core engine, or download `src_win.zip` from the Releases page and extract it manually
6. If needed, set the installation path using **Set Installation Path** in the plugin

### Ubuntu/Linux (22.04+)

1. Install system dependencies:
   ```bash
   sudo apt install libspatialindex-dev python3-pandas
   ```

2. Open QGIS
3. Go to **Plugins > Manage and Install Plugins > Settings**
4. Add a new plugin repository with the URL:
   ```
   https://raw.githubusercontent.com/NHAZCA/ps_toolbox_releases/main/plugins.xml
   ```
5. Search for **PSToolbox-IRIDE** in the plugin list and install it
6. Open the plugin from the toolbar and use **Download Software** to download the core engine, selecting the destination folder
7. If needed, set the installation path using **Set Installation Path** in the plugin

### Licensing

PS Toolbox uses a hardware-locked licensing system. To activate a license:

1. You will receive a `.key` license file from NHAZCA
2. Copy the `.key` file into the folder where the software was downloaded
3. From the plugin, activate the license by selecting the `.key` file

To request a license, contact NHAZCA providing the machine identifier:

- **Windows** (run in PowerShell):
  ```powershell
  Get-CimInstance -ClassName Win32_ComputerSystemProduct | Select-Object -ExpandProperty UUID
  ```
- **Linux** (run in terminal):
  ```bash
  cat /sys/class/net/*/address
  ```
  Provide the first line that is not `00:00:00:00:00:00`.

### Command-Line Usage

The core engine can also be used standalone:

```bash
# Windows
PS_toolbox.exe -p <processing_type> -f <parameters.json>
PS_toolbox.exe -v

# Linux
./PS_toolbox -p <processing_type> -f <parameters.json>
./PS_toolbox -v
```

## System Requirements

- **Operating System**: Windows 10/11 or Ubuntu 22.04+
- **QGIS**: Version 3.x or higher (for plugin)
- **Memory**: 8 GB RAM minimum (16 GB recommended)
- **Disk Space**: 2 GB for installation + space for data processing

## Processing Modules

- **Datafusion**: Multi-dataset fusion using spatial interpolation
- **Format**: Data format conversion and preprocessing (ARPA, CSV, Parquet)
- **Buildings**: Building-specific displacement analysis with IRIDE support
- **Download EGMS**: European Ground Motion Service data downloader
- **Vectorial Decomposition**: 3D displacement from multiple viewing geometries
- **Linear Infrastructure**: Infrastructure monitoring (roads, railways)
- **KMZ Export**: Google Earth export with Level of Detail support
- **Filtering**: Spatial and temporal data filtering
- **Heatmap**: Displacement heatmap generation
- **TCD**: Temporal Coherence Detection analysis
- **Sections**: Cross-section analysis
- **Gradient**: Displacement gradient calculation

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for version history and release notes.

## Issues & Support

For bug reports and feature requests, please contact NHAZCA.

---

Copyright NHAZCA. All rights reserved.
