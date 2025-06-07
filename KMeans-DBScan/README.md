# 🚗 Uber Trip Analysis - Clustering and Visualization

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/58/Uber_logo_2018.svg/1024px-Uber_logo_2018.svg.png" alt="UBER LOGO" width="50%" />

## 📋 Project Overview

This project presents a comprehensive analysis of Uber trip data for 2014, using advanced clustering techniques to identify high-demand areas and urban mobility trends.

**Objective:**

To analyze Uber trip trends through geographic clustering to optimize vehicle dispatch and understand urban demand. ## 🎯 Features
- **Temporal analysis** of daily/hourly trips
- **Geographic clustering** with K-Means and DBSCAN
- **Interactive visualizations** with density maps
- **Clustering algorithm comparison**
- **Identification of hot spots** for demand

## 🔧 Technologies used

### Main libraries

- **Pandas/NumPy** - Data manipulation
- **Plotly** - Interactive visualizations and maps
- **Matplotlib** - Static charts
- **Scikit-learn** - Clustering algorithms and metrics
- **Yellowbrick** - Clustering visualization

### Implemented algorithms

- **K-Means** - Centroid-based clustering with optimal cluster count
- **DBSCAN** - Density-based clustering with cluster detection Noise

## 📊 Data Structure

### Source Files (2014)
```
├── uber-raw-data-apr14.csv # April 2014 Data
├── uber-raw-data-may14.csv # May 2014 Data
├── uber-raw-data-jun14.csv # June 2014 Data
├── uber-raw-data-jul14.csv # July 2014 Data
├── uber-raw-data-aug14.csv # August 2014 Data
└── uber-raw-data-sep14.csv # September Data 2014
```

### Data Columns

- **date**: Date and time of the course
- **lat**: Latitude of the pickup point
- **lon**: Longitude of the pickup point
- **base**: Uber base code

## 🚀Installation and Configuration

## 📈 Analysis Pipeline

### 1. 📊 Data Loading and Merging
- Importing 6 months of data (April to September 2014)
- Merging into a single dataset
- Creating time columns (hour, day, month)

### 2. 📋 Stratified Sampling
- 5% data sampling
- Stratification by geographic area and base
- Optimizing computational performance

### 3. 🎨 Exploratory Visualizations
- **Basic Analysis**: Number of trips by base code
- **Temporal Analysis**: Daily and Hourly Trends
- **Density Maps**: High Demand Areas
- **Interactive Heat Maps**: Spatio-temporal Evolution

### 4. 🤖 Geographic Clustering

#### K-Means
- **Elbow Method** to Determine the Optimal Number of Clusters
- **6 Optimal Clusters** Identified
- Centroid and Cluster Visualization

#### DBSCAN
- **Density-Based Clustering**
- **13 Clusters** Naturally Detected
- Noise Point Identification

### 5. 📊Evaluation and Comparison
- **Silhouette Score** for DBSCAN
- **Davies-Bouldin Index** for Cluster Quality
- Comparison of Algorithmic Approaches

## 📈Main Results

### K-Means Clustering
- **6 Optimal Clusters** (Elbow Method)
- **Inertia: 98,636** (compact clusters)
- Forced spherical structure

### DBSCAN Clustering
- **13 clusters** detected naturally
- **Noise points** identified
- **Silhouette Score** calculated
- **Davies-Bouldin Index** evaluated

### 🏆 Algorithm Comparison

## 🎨 Available Visualizations

### Temporal Analysis
- Trip Histograms by Baseline
- Day/Hour Heatmaps
- Density Maps by Day of the Week

### Geographic Clustering
- Colored Cluster Scatterplots
- Mapbox Interactive Maps
- Centroids and Noise Points

## 🎯 Practical Applications

### For Uber
- **Cluster-Based Fleet Optimization**
- **Dynamic Pricing** by Demand Zone
- **Spatio-Temporal Forecasting of Demand**

### For Cities
- Mobility-Based Urban Planning
- Rush Hour Traffic Management
- Motion Flow Analysis

## 🔮Future Improvements

- Temporal Clustering (adding the time dimension)
- Advanced Algorithms (HDBSCAN, Gaussian Mixture)
- Real-Time Demand Forecasting
- Interactive Interface for Exploration

## 📊 Performance Indicators

### K-Means
- Clusters: 6 optimal
- Inertia: 98,636 (compact)
- Structure: Uniform Spherical

### DBSCAN
- Clusters: 13 detected
- Noise Points: identified
- Flexibility: variable shapes

## 🏷️ Technique Configuration

### DBSCAN Parameters
- **eps:** 0.01 (maximum distance)
- **min_samples:** 5 (minimum number of points per cluster)

### Sampling
- **Size:** 5% of the original data
- **Method:** stratified by area and frame

## ⚠️ Limitations

- **Memory constraints** limit the parameters
- **Data limited** to 6 months of 2014
- **Sampling** may mask some patterns

## 📞 Conclusion

**DBSCAN vs. K-Means:**
- **DBSCAN (13 clusters):** Natural detection of high-density areas
- **K-Means (6 clusters):** Forced structure but simpler

**Recommendation:**
Use DBSCAN for exploratory analysis and K-Means for operational implementation, depending on business needs.

## 📚 Key Results

### Algorithm Behavior
- **K-Means** enforces spherical structures and minimizes inertia
- **DBSCAN** identifies natural density-based clustering
- **More clusters with DBSCAN** indicate naturally fragmented patterns

### Business Impact
- **Identify hotspots** for optimal vehicle positioning
- **Temporal models** for dynamic resource allocation
- **Demand prediction** for operational efficiency

## 🚀 Getting Started

1. **Configure the environment** with the required libraries
2. **Load and merge** the 6 months of Uber data
3. **Create temporal features** and geographic samples
4. **Run clustering algorithms** with optimal parameters
5. **Generate visualizations** and compare results
6. **Apply insights** to strategies operational

---

## 👤 Author

Project by **Andriana**  
🔗 GitHub: [https://github.com/Andrianiniaina/0-Machine-Learning-Projects]
