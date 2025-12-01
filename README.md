# Dimensionality Reduction & Spectral Clustering  

## Overview
This project applies PCA, K-Means clustering, and vegetation–water index computations (NDVI/NDWI) to geospatial spectral data. The objective is to reduce dimensionality from 7 spectral bands to 3 principal components and compare clustering performance between original and PCA-reduced datasets.

## Tools & Libraries
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn (PCA, KMeans, Silhouette)
- Yellowbrick (Elbow Visualizer)
- SciPy (assignment & contingency)
- mpl_toolkits & matplotlib color utilities

## Dataset & Features
- Input file: `Processed_Assen_RS_data.csv`
- Pixel grid size: 172 × 284
- Bands used: Band1 – Band7
- Coordinates: Latitude & Longitude
- Derived indices:
  - NDVI = vegetation index
  - NDWI = water index

## Project Workflow

### 1. Data Import & Cleaning
- Loaded CSV file
- Converted columns to numeric
- Imputed missing band values using mean fill
- Verified expected pixel count

### 2. Exploratory Data Analysis
- Correlation matrix between spectral bands
- Summary statistics of pixel distributions

### 3. Feature Engineering
- Computed NDVI and NDWI
- Reshaped to 172×284 arrays for spatial mapping

### 4. PCA Dimensionality Reduction
- Standardized bands with StandardScaler
- Applied PCA (n=3)
- Examined variance explained & loadings
- Generated scree plot and spatial PC maps

### 5. Optimal K Selection
- Tested k = 2–10
- Evaluated inertia & silhouette score
- Yellowbrick elbow validation
- Final K value determined

### 6. K-Means Clustering
- Applied clustering to original scaled spectra
- Applied clustering to PCA-transformed data
- Compared silhouette scores:
  - Original: 0.357
  - PCA: 0.384 (better separation)

### 7. Label Alignment
- Built contingency matrix
- Applied Hungarian algorithm
- Created overlap heatmap

### 8. Spatial Visualizations
- PCA spatial maps
- Cluster spatial maps for both datasets
- PCA-RGB composite visualization
- NDVI & NDWI contour overlays

## Key Findings
- PCA improved clustering quality and separation of spectral classes.
- Original data clusters contained more subtle localized variability.
- PCA clusters displayed smoother large-scale transitions.
- Tradeoff: detail precision vs spectral redundancy reduction.

## How to Run
1. Clone repository  
2. Install dependencies:  

