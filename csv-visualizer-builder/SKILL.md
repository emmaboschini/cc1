---
name: csv-visualizer-builder
description: Builds and publishes custom CSV visualizers using Leaflet.js and dark-mode styling. Use when the user wants to create a web app to explore a specific CSV dataset with map visualization, filtering, and stats.
---

# CSV Visualizer Builder

This skill provides a standard template and workflow for creating interactive, map-based CSV visualizers.

## Core Functionality
- **Map Visualization:** Automatic plotting of lat/lng coordinates using Leaflet.js.
- **Smart Schema Detection:** Automatically maps common column names (e.g., `latitude`, `longitude`, `country`) to functional fields.
- **Interactive Filtering:** Built-in country/location filters and dynamic statistics.
- **Data Ingestion:** Supports drag-and-drop file uploads and copy-paste CSV data.

## Workflow

### 1. Analyze the CSV
Before building, examine the user's CSV to identify the columns for:
- **Coordinates:** `lat`, `lng`, etc.
- **Labels:** `name`, `title`, `country`, etc.
- **Metrics:** `dead`, `displaced`, `severity`, etc.

### 2. Scaffold the App
- Create a new directory under `apps/` (e.g., `apps/my-dataset/`).
- Copy `assets/template/visualizer.html` to `apps/my-dataset/index.html`.
- Update the `SAMPLE_DATA` constant in the script section with the first few rows of the user's CSV.

### 3. Customize Logic (Optional)
If the CSV has unique column names not covered by the default `findColumn` mappings:
- Update the `*_COLUMNS` arrays in the script section.
- Adjust `getSeverityColor` or `getMarkerSize` if different metrics are more relevant.

### 4. Publishing
Follow the [publishing-workflow.md](references/publishing-workflow.md) guide to deploy on GitHub Pages.

## Constraints
- **Branch:** Always push to `main`.
- **URL Privacy:** Each app must reside in its own subdirectory to avoid overwriting the root `index.html`.
