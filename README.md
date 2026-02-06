# 📊 Tutorial: Geographically Weighted Regression (GWR)

Guest lecture materials for **GEOG 475: Advanced GIS**  
**Yifan Yang, Department of Geography, Texas A&M University**
---

## 🔎 Overview

This repository provides a structured introduction to **Geographically Weighted Regression (GWR)**—a spatial regression technique designed to model **spatially varying relationships** (i.e., spatial non-stationarity).

Unlike traditional global regression models, GWR allows regression coefficients to vary across geographic space, enabling researchers to explore **local variations in geographic processes** that would otherwise be obscured by global averages.

The materials are designed for a **50-minute advanced GIS lecture**, combining conceptual foundations with a hands-on Python-based demonstration.

<p align="center">
  <img src="https://raw.githubusercontent.com/rayford295/Tutorial_Geographically-Weighted-Regression/main/slides%20%26%20figures/GWR.png" 
       alt="Geographically Weighted Regression (GWR) Overview" 
       width="500">
</p>

---

## 🧭 Table of Contents

- [📘 What is GWR?](#-what-is-gwr)
- [🧠 Key Concepts](#-key-concepts)
- [🔬 Hands-on Tutorial (Code)](#-hands-on-tutorial-code)
- [🧑‍🏫 Lecture Slides and Figures](#-lecture-slides-and-figures)
- [⏱ Suggested Teaching Flow](#-suggested-teaching-flow)
- [⚠️ Methodological Notes](#-methodological-notes)
- [🎓 Intended Audience](#-intended-audience)
- [🔄 Reuse and Adaptation](#-reuse-and-adaptation)
- [📚 Recommended Resources](#-recommended-resources)
- [🧪 Example Use Cases](#-example-use-cases)
- [📝 Citation](#-citation)


---
### 🎥 Lecture Video

<p align="center">
  <a href="https://www.youtube.com/watch?v=Hd-h4u4WzNg">
    <img src="https://img.youtube.com/vi/Hd-h4u4WzNg/hqdefault.jpg" width="660">
  </a>
</p>


---

## 📘 What is GWR?

**Geographically Weighted Regression (GWR)** is a local spatial regression method that:

- Estimates **location-specific regression coefficients**
- Explicitly accounts for **spatial non-stationarity**
- Produces spatial surfaces of model parameters and diagnostics (e.g., local R²)

Rather than assuming a single global relationship, GWR addresses the question:

> *How do relationships between variables vary across space?*

GWR has been widely applied in geography, environmental science, urban studies, public health, transportation, and related spatial disciplines.

---

## 🧠 Key Concepts

### 1) Spatial Non-Stationarity
Conventional regression models assume relationships are constant across space.  
GWR relaxes this assumption by allowing relationships to vary **locally**, reflecting heterogeneous geographic processes.

### 2) Spatial Weighting and Kernel Functions
At each target location, nearby observations are weighted more heavily than distant ones using a kernel function, such as:

- Gaussian kernel
- Bisquare kernel

This implements the principle of **distance decay** in local model estimation.

### 3) Bandwidth Selection
The bandwidth controls the spatial scale of locality:

- Small bandwidth → highly local model (risk of overfitting)
- Large bandwidth → model approaches global regression

Bandwidth is typically selected using:
- AICc-based optimization
- Cross-validation (CV)

### 4) Local Diagnostics
GWR produces spatially explicit diagnostics, including:

- Local regression coefficients
- Local R² (local model fit)
- Residuals and influence measures

These outputs must be interpreted **spatially and contextually**, not as global summaries.

---

## 🔬 Hands-on Tutorial (Code)

This repository includes a **fully reproducible, Colab-ready Python notebook**
demonstrating a complete **OLS → GWR analytical workflow** using a simulated
**Urban Heat Island (Land Surface Temperature, LST)** example.

📂 **Location:**  
`code/0206_GWR.ipynb`

### The notebook demonstrates

- Simulation of city-like spatial sampling points  
- Construction of urban explanatory variables (NDVI, building density, distance to CBD)  
- Fitting a **global OLS regression model**  
- Diagnosing spatial clustering in OLS residuals (Moran’s I)  
- Fitting a **Geographically Weighted Regression (GWR)** model  
- Visualization of:
  - Spatially varying coefficients
  - Local R²
  - Residual patterns (OLS vs. GWR)

The notebook is designed for **in-class demonstration** and emphasizes
**interpretation, diagnostics, and methodological reasoning**, rather than
black-box model execution.

> ⚠️ Note  
> The dataset is **synthetic but geographically realistic**, intentionally
> constructed to exhibit spatial non-stationarity for instructional purposes.

---

## 🧑‍🏫 Lecture Slides and Figures

The repository also contains **lecture slides and supporting figures**
used in the guest lecture for **GEOG 475: Advanced GIS**.

📂 **Location:**  
`slides & figures/`

These materials support the **conceptual component** of the lecture and address:

- Motivation for spatial regression
- Limitations of global regression models
- Conceptual foundations of GWR
- Interpretation of local coefficients and diagnostics
- Common pitfalls and methodological misuse of GWR

The slides are designed to be used **in conjunction with the notebook**
to form a coherent lecture–demonstration sequence.

---

## ⏱ Suggested Teaching Flow

| Time        | Component                                 | Materials |
|-------------|-------------------------------------------|-----------|
| 0–10 min    | Motivation & spatial regression concepts  | Slides    |
| 10–20 min   | Global vs. local regression (OLS vs. GWR) | Slides    |
| 20–30 min   | Core GWR concepts (kernel, bandwidth)     | Slides    |
| 30–45 min   | Hands-on OLS → GWR demonstration          | Notebook  |
| 45–50 min   | Interpretation, limitations, discussion   | Slides    |

---

## ⚠️ Methodological Notes

When applying GWR, users should be aware that:

- GWR is primarily **exploratory and descriptive**
- Local coefficients may be unstable under multicollinearity
- Bandwidth selection strongly influences results
- GWR does **not** imply causal relationships by itself

These issues are explicitly discussed in both the slides and the notebook.

---

## 🎓 Intended Audience

This tutorial is intended for:

- Upper-level undergraduate and graduate students in GIS / Geography
- Students with foundational knowledge of:
  - Linear regression
  - Spatial data concepts
  - Python or statistical software (helpful but not required)

---

## 🔄 Reuse and Adaptation

Instructors are encouraged to:

- Reuse and adapt the slides for teaching
- Modify the notebook for alternative case studies
  (e.g., housing prices, public health, environmental exposure)
- Extend the workflow using ArcGIS Pro, PySAL, or other spatial analysis tools

Attribution is appreciated.

---

## 📚 Recommended Resources

### ESRI / ArcGIS Pro
- **How Geographically Weighted Regression (GWR) Works**  
  https://pro.arcgis.com/en/pro-app/latest/tool-reference/spatial-statistics/how-geographicallyweightedregression-works.htm

### Academic Overview
- **Geographically Weighted Regression (ScienceDirect Topic Page)**  
  https://www.sciencedirect.com/topics/earth-and-planetary-sciences/geographically-weighted-regression

### Technical Guide (PDF)
- **GWR Technical Guide (University of Bristol)**  
  https://www.bristol.ac.uk/media-library/sites/cmpo/migrated/documents/gwr.pdf

---

## 🧪 Example Use Cases

| Field                 | Example Application                                  |
|-----------------------|------------------------------------------------------|
| Urban Studies         | Spatially varying housing price determinants         |
| Public Health         | Local risk factors for disease outcomes              |
| Environmental Science | Pollutant–health associations with spatial variation |
| Transportation        | Local drivers of congestion or accessibility         |

---

## 📝 Citation

If you use or reference GWR in academic work, consider citing:

Brunsdon, C., Fotheringham, A. S., & Charlton, M. (1996).  
*Geographically Weighted Regression: A Method for Exploring Spatial Non-Stationarity.*  
**Geographical Systems**, 8, 161–185.
