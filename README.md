# PS Toolbox - Releases

  Public releases for **PS Toolbox**, a Persistent Scatterers (PS) data post-processing application for InSAR
  (Interferometric Synthetic Aperture Radar) analysis.

  ## 📥 Downloads

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

  ## 🔧 Installation

  ### QGIS Plugin Installation

  1. Download `PSToolbox-IRIDE.zip` from the latest release
  2. Open QGIS
  3. Go to: **Plugins** → **Manage and Install Plugins** → **Install from ZIP**
  4. Select the downloaded `PSToolbox-IRIDE.zip`
  5. Click **Install Plugin**

  ### Core Engine Installation

  1. Download `src_win.zip` (Windows) or `src_ubu.zip` (Ubuntu/Linux) from the latest release
  2. Extract to your desired location
  3. Set software installation path in the QGIS plugin

  For command-line usage:
  ```bash
  # View help (Windows / Linux)
  PS_toolbox.exe --help        # Windows
  ./PS_toolbox --help           # Linux

  # Run with parameters file
  PS_toolbox.exe -p <processing_type> -f <parameters.json>    # Windows
  ./PS_toolbox -p <processing_type> -f <parameters.json>       # Linux

  # Show version
  PS_toolbox.exe -v             # Windows
  ./PS_toolbox -v               # Linux

  📋 System Requirements

  - Operating System: Windows 10/11 or Linux
  - QGIS: Version 3.x or higher (for plugin)
  - Memory: 8 GB RAM minimum (16 GB recommended)
  - Disk Space: 2 GB for installation + space for data processing

  🔑 Licensing

  PS Toolbox uses a hardware-locked licensing system. For licensing information:

  # Request license
  PS_toolbox.exe -r <your_email>

  # Activate license
  PS_toolbox.exe -la <license_file>

  # Check license info
  PS_toolbox.exe -li

  📖 Features

  Processing Modules

  - Datafusion: Multi-dataset fusion using spatial interpolation
  - Format: Data format conversion and preprocessing (ARPA, CSV, Parquet)
  - Buildings: Building-specific displacement analysis with IRIDE support
  - Download EGMS: European Ground Motion Service data downloader
  - Vectorial Decomposition: 3D displacement from multiple viewing geometries
  - Linear Infrastructure: Infrastructure monitoring (roads, railways)
  - KMZ Export: Google Earth export with Level of Detail support
  - Filtering: Spatial and temporal data filtering
  - Heatmap: Displacement heatmap generation
  - TCD: Temporal Coherence Detection analysis
  - Sections: Cross-section analysis
  - Gradient: Displacement gradient calculation

  📝 Changelog

  See CHANGELOG.md for version history and release notes.

  🐛 Issues & Support

  For bug reports and feature requests, please contact NHAZCA.

  📄 License

  Copyright © NHAZCA. All rights reserved.

  ---
  Developed by NHAZCA

  ---
