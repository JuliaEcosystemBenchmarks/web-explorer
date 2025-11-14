# Julia Ecosystem Benchmarks Explorer

## Overview

This project provides an interactive web-based visualization tool for exploring Julia ecosystem benchmarking data. It creates dynamic, filterable charts to analyze Time-To-First-X (TTFX) performance metrics across different Julia versions, packages, and tasks.

The explorer visualizes data from the [Julia Ecosystem Benchmarks](https://github.com/JuliaEcosystemBenchmarks/julia-ecosystem-benchmarks) project, which systematically tracks Julia performance metrics across versions and package ecosystem changes.

## Data Source

The visualization consumes CSV data directly from:
```
https://raw.githubusercontent.com/JuliaEcosystemBenchmarks/julia-ecosystem-benchmarks/refs/heads/jeb_logs/data/Julia-TTFX-Snippets/ttfx_snippets_data.csv
```

This dataset contains performance measurements including:
- **Time Metrics**: precompile_time, loading_time, task_time
- **CPU Metrics**: precompile_cpu, task_cpu  
- **Memory Metrics**: precompile_resident, task_resident
- **Metadata**: package_name, task_name, date, julia_version, hostname, hash

## Key Features

### Interactive Controls
- **Package Selection**: Multi-select dropdown to filter by specific packages or view all
- **Task Selection**: Multi-select dropdown to filter by specific benchmark tasks or view all
- **Metric Selection**: Choose time and memory metrics for side-by-side comparison

### Visualizations
- **Side-by-side Charts**: Time performance (left) and memory usage (right)
- **Time Series Analysis**: X-axis shows dates to track performance trends over time
- **Julia Version Differentiation**: Color-coded data points distinguish different Julia versions
- **Interactive Tooltips**: Hover for detailed information about each data point

### Data Filtering
- Cross-filtering across package, task, and metric dimensions
- Real-time chart updates based on selections
- Handles large datasets efficiently

## Technical Implementation

### Dependencies
- **D3.js v7**: Core visualization library
- **Modern Browser**: ES6+ support required for async/await and modern JS features

### Architecture
- **Single HTML File**: Self-contained application with embedded CSS and JavaScript
- **Client-side Data Processing**: Fetches and processes CSV data in the browser
- **Responsive Design**: Adaptive layout for different screen sizes

### Julia Version Support
The explorer supports visualization of performance data across Julia versions:
- 1.8.x series (1.8.0 - 1.8.5)
- 1.9.x series (1.9.0 - 1.9.4) 
- 1.10.x series (1.10.0 - 1.10.5)
- 1.11.x series (1.11.0 - 1.11.6)
- 1.12.x series (1.12.0+)

Each version is assigned a distinct color for visual differentiation in the charts.

## Usage

### Getting Started
1. Open `index.html` in a modern web browser
2. Wait for data to load from the remote CSV source
3. Use the control panel to filter data by package, task, and metrics
4. Explore the interactive charts with tooltips and zoom functionality

### Analyzing Performance Trends
- **Version Comparisons**: Compare performance across Julia versions using color coding
- **Package Analysis**: Filter to specific packages to understand their performance characteristics
- **Task Benchmarking**: Focus on particular benchmark tasks to track optimization progress
- **Timeline Analysis**: Observe performance changes over time periods

### Troubleshooting
- **Network Issues**: Ensure internet connectivity for CSV data fetching
- **Browser Compatibility**: Use modern browsers with ES6+ support
- **Data Loading**: Check browser console for detailed error messages if charts don't appear

## File Structure

```
jeb-explorer/
├── index.html          # Main application file
├── CLAUDE.md          # This documentation
└── .git/              # Git repository
```

## Development Notes

### Console Logging
The application includes comprehensive console logging for debugging:
- Data loading progress and validation
- Filtering operations and results  
- Chart creation and rendering steps
- Error handling and diagnostics

### Color Scheme
Uses D3.js v7 compatible color schemes (Category10, Dark2, Set3) to ensure sufficient color variation for Julia version differentiation.

### Data Processing Pipeline
1. **Fetch**: Load CSV data from remote GitHub repository
2. **Parse**: Convert string data to appropriate types (numbers, dates)
3. **Filter**: Apply user selections for packages, tasks, metrics
4. **Visualize**: Create D3.js charts with interactive features

## Related Projects

This explorer complements the main [Julia Ecosystem Benchmarks](https://github.com/JuliaEcosystemBenchmarks/julia-ecosystem-benchmarks) project by providing:
- Interactive data exploration vs. static analysis
- Web-based accessibility vs. local Julia script execution
- Real-time filtering vs. pre-generated plots
- Cross-platform visualization vs. Julia environment dependency

For more information about the benchmarking methodology and data collection, see the original project's documentation.