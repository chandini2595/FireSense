## 1.1 Objective Functions to Identify the Golden Cluster
To determine the **golden cluster** of high-risk wildfire regions, we define the following **objective functions**:

1. **Fire Risk Score (FRS) Optimization**
   
   - **FRI (Fire Risk Index):** Measures the probability of wildfire occurrence.
   - **CEI (Climatic & Environmental Index):** Captures environmental factors (temperature, humidity, wind speed, etc.).
   - **Stopping Criterion:** Stop re-clustering when **variance of FRS across clusters** is minimized.

3. **Fire Severity Score (FSS) Optimization**
   
   - **GIS_ACRES:** Represents the total area burned in each cluster.
   - **Stopping Criterion:** Stop re-clustering if **change in FSS after re-clustering is below a threshold (\(\epsilon_2\))**.

---

## 1.2 Compute SSE and Silhouette Score
To evaluate clustering performance, we calculate:

- **Sum of Squared Errors (SSE)**
  - Measures compactness of clusters (lower is better).

- **Silhouette Score**
  - \( a \): Average intra-cluster distance.
  - \( b \): Average nearest-cluster distance.
  - Score closer to **1** indicates well-defined clusters.

---

## 2. Writeup on the Project

### 2.1 Data Narrative: Key Questions
1. **Where are the high-risk wildfire zones?**
   - Identify regions prone to wildfires based on historical data.
  
2. **What environmental conditions contribute to wildfire outbreaks?**
   - Analyze temperature, humidity, wind speed, and vegetation.

3. **Can we predict the severity of a wildfire?**
   - Forecast the expected **burned area (GIS_ACRES)** using ML models.

### Business & ML Tasks

- **Business Task:**  
  - Provide early wildfire risk assessment for **government agencies, emergency responders, and insurance companies**.

- **Machine Learning Task:**  
  - **Clustering:** Group geographic locations based on fire risk using climatic conditions (K-Means, Fractal).  


### Exploratory Data Analysis & Visualization (EDAV)

- **Data Structure:**
  - Time-series sensor readings (temperature, humidity, wind speed).
  - Geospatial data (latitude, longitude of fire occurrences).
  - Historical wildfire records (size, duration, cause).

- **Visualizations:**
  - **Heatmaps:** Identify high-risk areas.
  - **Scatter plots:** Show correlation between environmental factors and wildfire occurrences.
  - **Time-series plots:** Analyze seasonal trends.

- **Distribution Analysis:**
  - **Fire Risk Index (FRI):** Check for skewness in risk distribution.
  - **Burned Area (GIS_ACRES):** Assess the range and spread of fire severity.

---

## 2.2 Datasets

#### **Dataset Used: [FireSense - combined.csv](https://github.com/chandini2595/FireSense/blob/main/Fractal%20Clustering/combined.csv)**
- **Description:** This dataset contains wildfire risk factors collected from various sources.
- **Features:**
  - **Geospatial:** Latitude, Longitude
  - **Environmental:** Temperature, Wind Speed, Humidity, Vegetation Index
  - **Wildfire Information:** Fire Occurrence, GIS_ACRES (Burned Area)
  - **Climatic Factors:** Precipitation, Drought Index
- **Usage:** This dataset is used for clustering fire-prone regions and predicting fire severity.

---

## 2.3 Objective Functions for Finding the Golden Cluster

To determine the **golden cluster** (i.e., the optimal segmentation of wildfire-prone areas), we evaluate clusters using:

1. **SSE & Silhouette Score**
   - **Goal:** Ensure tight clustering with high silhouette scores.
   - **Stopping Criterion:** Stop re-clustering when SSE stabilizes and Silhouette Score is maximized.

2. **Fire Risk Score (FRS)**
   - **Goal:** Minimize intra-cluster variance in FRS.

3. **Fire Severity Score (FSS)**
   - **Goal:** Ensure the **most severe fire zones** are well-grouped.

By combining these **three** criteria, we define the most **meaningful and actionable clusters** for wildfire risk mitigation.
