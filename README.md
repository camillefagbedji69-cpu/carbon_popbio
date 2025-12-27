# Carbon-Transition-Dynamics: Matrix Modeling of LULC Carbon Flux

## 📌 Context & Overview
Land Use and Land Cover (LULC) changes are the primary drivers of carbon stock fluctuations. To manage terrestrial carbon sinks effectively, we must understand not just where carbon is, but how it flows during land transitions. This project integrates **Copernicus LULC data (2015-2019)** with **InVEST Carbon models** to quantify carbon gains and losses through a matrix-based transition framework.

## 🎯 Objectives
* **Carbon Flux Quantification:** Measuring net carbon variations per pixel across LULC classes.
* **Transition Analysis:** Identifying "Carbon-Positive" transitions (e.g., Agriculture → Forest).
* **Matrix Experimentation:** Testing the feasibility of demographic matrix tools (`popbio`) for environmental flux ranking.

## 🛠️ Tech Stack & Methodology
* **Language:** R 📊
* **Core Tools:** `InVEST Carbon Storage`, `popbio`, `ggplot2` (Heatmaps).
* **Analytical Workflow:**
    1. **Change Detection:** Calculating the carbon delta ($\Delta C$) per pixel between 2015 and 2019.
    2. **Transition Weighting:** Constructing LULC transition matrices where each cell is weighted by its mean carbon variation.
    3. **Mathematical Testing:** Applying Eigen-analysis to identify "key-player" classes in carbon sequestration dynamics.



## 🚀 Key Results
* **Carbon Hotspots:** Closed and semi-open forest classes (Codes 114 to 126) remain the critical pillars for carbon gain.
* **Winning Transitions:** Significant carbon accumulation was verified in **Agriculture → Forest** and **Herbaceous → Forest** pathways.
* **Methodological Discovery:**
    * Standard population biology tools (`popbio`) are optimized for positive growth rates.
    * Including negative values (carbon loss) leads to mathematical instability ($NaN/Inf$).
    * **Proposed Solution:** High-resolution separation of "Gain Matrices" and "Loss Matrices" provides a more stable and interpretable ranking of ecological importance.
* **Strategic Ranking:** Identified the "Crucial Classes" that maintain landscape-level carbon stability despite localized degradation.

## 🔮 Perspectives for Improvement
* **Multi-Temporal Series:** Using decade-long data to build more robust transition probabilities.
* **Integrated Flux Modeling:** Developing custom R functions to handle negative ecological transitions without generating mathematical artifacts.
* **Spatio-Temporal Visualization:** Creating dynamic flow diagrams (Sankey diagrams) to visualize carbon migration between land classes.
* **Biomass Proxy:** Incorporating NDVI/Biomass indices to refine carbon estimates within transition cells.
