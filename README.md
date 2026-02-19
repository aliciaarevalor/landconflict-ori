# land use change and land use conflicts in Arauca, Casanare, and Meta from 2000 to 2022

## Project Overview

This repository contains a comprehensive geospatial analysis workflow for identifying land use dynamics and conflicts in **Arauca**, **Casanare**, and **Meta** departments of Colombia, covering the period from **2000 to 2022**.

The project performs a comparative spatial analysis between **Land Use/Land Cover (LULC)** and **Land Use Vocation** to quantify conflicts and understand how land management practices align with recommended land use suitability.

---

## Study Area & Temporal Coverage

- **Geographic Focus**: Arauca, Casanare, and Meta (Colombia)
- **Time Period**: 2000, 2010, and 2022

---

## Workflow Overview

The project is organized into four main Jupyter notebooks in sequential order:

### 1. **preprocessing.ipynb** 
**Data preparation and standardization**

This notebook prepares raw geospatial data for analysis:

- **Reproject geospatial data** to a consistent coordinate system (EPSG:9377)
- **Clip land cover maps** by department boundaries
- **Standardize land cover classification** into Level 2 categories with consistent coding
- **Create Land Cover × Land Use Vocation intersections** for conflict analysis
- **Derive Level 1 classifications** from Level 2 data

**Key Outputs**:
- Standardized land cover GeoPackages (Level 2)
- Land cover × land use vocation intersections
- Aggregated land cover classifications (Level 1)

---

### 2. **landcover.ipynb** 
**Multi-temporal land cover change analysis**

This notebook analyzes land use and land cover transitions:

- **Area calculations** by land cover class and year
- **Net change analysis** (2000-2022) with gain/loss visualization
- **Multi-year trends** showing changes across 2000, 2010, and 2022
- **Sankey diagrams** illustrating class transitions and flows
- **Department-level summaries** and combined analysis for all three departments

**Key Outputs**:
- Land cover area change CSV files (by department and combined)
- Bar charts showing area changes per class
- Sankey diagrams showing land cover transitions

**Land Cover Classes**:
- Artificial surfaces (Urban, Industrial, Mining, etc.)
- Agricultural areas (Arable land, Pastures, Permanent crops, etc.)
- Forest and semi-natural areas (Forest, Shrubland, etc.)
- Wetlands
- Water bodies

---

### 3. **landconflict.ipynb** 
**Land use conflict identification and quantification**

This notebook implements a geographic decision-support model to classify and analyze land use conflicts:

- **Conflict classification logic** comparing actual land cover against recommended land use vocation
- **Three conflict levels**:
  - 🔴 **High Conflict**: Severe mismatch between land cover and vocation
  - 🟠 **Moderate Conflict**: Partial misalignment
  - 🟢 **No Conflict**: Appropriate land management practices

- **Temporal transition analysis** (2000→2010, 2010→2022, 2000→2022)
- **Gain/loss quantification** of each conflict category over time
- **Multi-temporal visualization** of conflict patterns

**Conflict Mapping Logic**:
The conflict classification depends on land use vocation type:
- **Agricultural/Livestock/Agroforestry**: Pastures, Heterogeneous agriculture acceptable; Urban, Industrial, Mining = High conflict
- **Forestry/Conservation**: Natural vegetation favored; Urban, Agricultural = High conflict  
- **Urban Areas**: Built-up surfaces required; Natural vegetation = High conflict
- **Water bodies**: Protected; Development = High conflict

**Key Outputs**:
- Conflict GeoPackages (normalized and with change polygons)
- Conflict transition matrices and summaries
- Gain/loss spatial layers by conflict category
- Conflict percentage tables by department

---

### 4. **plot.ipynb** 
**Publication-ready visualizations**

This notebook creates final cartographic products:

- **Multi-panel maps** (3 departments × 3 time periods = 9 panels)
- **Conflict visualization** with color-coded conflict levels
- **Land cover overlay** highlighting artificial surfaces and water bodies
- **Multi-legend display** for comprehensive map interpretation
- **High-resolution PDF export** 

---


## Key Features & Outputs

### Land Cover Analysis
✅ Multi-temporal area statistics (2000, 2010, 2022)  
✅ Net change calculations and trend analysis  
✅ Transition flows via Sankey diagrams  
✅ Department-level and regional summaries  

### Conflict Analysis
✅ Automated conflict classification (High/Moderate/None)  
✅ Temporal transition analysis  
✅ Gain/loss quantification  
✅ Spatial layers for GIS integration  

### Visualizations
✅ Time-series bar charts  
✅ Sankey diagrams showing class transitions  
✅ Multi-panel conflict maps  
✅ Publication-ready PDF outputs  

---

## Usage Instructions

**Run notebooks in order**:
   ```
   preprocessing.ipynb → landcover.ipynb → landconflict.ipynb → plot.ipynb
   ```

---




