# 🚗 Uber Rides Analysis - Clustering and Visualization

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/58/Uber_logo_2018.svg/1024px-Uber_logo_2018.svg.png" alt="UBER LOGO" width="50%" />

## 📋 Project Overview

This project presents a comprehensive analysis of Uber ride data for 2014, using advanced clustering techniques to identify high-demand zones and urban mobility patterns.

**Goal:** Analyze Uber ride patterns through geographic clustering to optimize vehicle distribution and understand urban demand.

## 🎯 Features

- **Temporal analysis** of rides by day/hour
- **Geographic clustering** with K-Means and DBSCAN
- **Interactive visualizations** with density maps
- **Algorithm comparison** for clustering
- **Hot zone identification** for demand

## 🔧 Technologies Used

### Main Libraries
- **Pandas/NumPy** - Data manipulation
- **Plotly** - Interactive visualizations and maps
- **Matplotlib** - Static plots
- **Scikit-learn** - Clustering algorithms and metrics
- **Yellowbrick** - Clustering visualization

### Implemented Algorithms
- **K-Means** - Centroid-based clustering with optimal cluster number
- **DBSCAN** - Density-based clustering with noise detection

## 📊 Data Structure

### Source Files (2014)
```
├── uber-raw-data-apr14.csv    # April 2014 data
├── uber-raw-data-may14.csv    # May 2014 data
├── uber-raw-data-jun14.csv    # June 2014 data
├── uber-raw-data-jul14.csv    # July 2014 data
├── uber-raw-data-aug14.csv    # August 2014 data
└── uber-raw-data-sep14.csv    # September 2014 data
```

### Data Columns
- **date** : Date and time of the ride
- **lat** : Latitude of pickup point
- **lon** : Longitude of pickup point
- **base** : Uber base code

## 🚀 Installation and Setup

### Prerequisites
```bash
pip install pandas numpy
pip install plotly matplotlib seaborn
pip install scikit-learn
pip install yellowbrick
```

### Google Colab Configuration
```python
from google.colab import drive
drive.mount('/content/drive')
```

## 📈 Analysis Pipeline

### 1. 📊 Data Loading and Merging
- Import 6 months of data (April to September 2014)
- Merge into single dataset
- Create temporal columns (hour, day, month)

### 2. 📋 Stratified Sampling
- 5% data sampling
- Stratification by geographic zone and base
- Performance optimization for computations

### 3. 🎨 Exploratory Visualizations
- **Base analysis**: Number of rides per base code
- **Temporal analysis**: Patterns by day and hour
- **Density maps**: High-demand zones
- **Interactive heatmaps**: Spatio-temporal evolution

### 4. 🤖 Geographic Clustering

#### K-Means
- **Elbow method** to determine optimal cluster number
- **6 optimal clusters** identified
- Visualization of centroids and groups

#### DBSCAN
- **Density-based clustering**
- **13 clusters** detected naturally
- Noise point identification

### 5. 📊 Evaluation and Comparison
- **Silhouette Score** for DBSCAN
- **Davies-Bouldin Index** for cluster quality
- Algorithmic approach comparison

## 📈 Main Results

### K-Means Clustering
- **6 optimal clusters** (elbow method)
- **Inertia: 98.636** (compact clusters)
- Forced spherical structure

### DBSCAN Clustering
- **13 clusters** detected naturally
- **Noise points** identified
- **Silhouette Score** calculated
- **Davies-Bouldin Index** evaluated

### 🏆 Algorithm Comparison

| Criteria | K-Means | DBSCAN |
|----------|---------|---------|
| **Number of clusters** | 6 (fixed) | 13 (automatic) |
| **Cluster shape** | Spherical | Variable density |
| **Noise handling** | No | Yes |
| **Flexibility** | Low | High |

## 🎨 Available Visualizations

### Temporal Analysis
- Histograms of rides per base
- Day/hour heatmaps
- Density maps by day of week

### Geographic Clustering
- Colored cluster scatter plots
- Interactive Mapbox maps
- Centroids and noise points

## 🔧 Usage

### Complete Execution
```python
# Data loading
for filename, dataname in files:
    df = pd.read_csv(path + filename)
    # Processing...

# K-Means Clustering
kmeans_model = KMeans(n_clusters=6, random_state=42)
kmeans_model.fit(X_data[['lat', 'lon']])

# DBSCAN Clustering
dbscan_model = DBSCAN(eps=0.01, min_samples=5)
dbscan_labels = dbscan_model.fit_predict(X_data[['lat', 'lon']])
```

### Key Functions
```python
elbow(X)                          # Elbow method
silhouette_score(X, labels)       # Silhouette score
davies_bouldin_score(X, labels)   # Davies-Bouldin index
```

## 📋 Business Insights

### Temporal Patterns
- **Demand peaks** identified by day/hour
- **Seasonal variations** over 6 months
- **Recurring high-activity zones**

### Operational Optimization
- **Optimal vehicle positioning**
- **Zone-based demand prediction**
- **Efficient resource allocation**

## 🎯 Practical Applications

### For Uber
- **Fleet optimization** based on clusters
- **Dynamic pricing** by demand zone
- **Spatio-temporal demand forecasting**

### For Cities
- **Urban planning** based on mobility
- **Traffic management** during peak hours
- **Movement flow analysis**

## 🔮 Future Improvements

- **Temporal clustering** (adding time dimension)
- **Advanced algorithms** (HDBSCAN, Gaussian Mixture)
- **Real-time demand prediction**
- **Interactive interface** for exploration

## 📊 Performance Metrics

### K-Means
- **Clusters:** 6 optimal
- **Inertia:** 98.636 (compact)
- **Structure:** Uniform spherical

### DBSCAN
- **Clusters:** 13 detected
- **Noise points:** Identified
- **Flexibility:** Variable shapes

## 🏷️ Technical Configuration

### DBSCAN Parameters
- **eps:** 0.01 (maximum distance)
- **min_samples:** 5 (minimum points per cluster)

### Sampling
- **Size:** 5% of original data
- **Method:** Stratified by zone and base

## ⚠️ Limitations

- **Memory constraints** limiting DBSCAN parameters
- **Limited data** to 6 months of 2014
- **Sampling** may mask certain patterns

## 📞 Conclusion

**DBSCAN vs K-Means:**
- **DBSCAN (13 clusters):** Natural detection of density zones
- **K-Means (6 clusters):** Forced but simpler structure

**Recommendation:** Use DBSCAN for exploratory analysis and K-Means for operational implementation based on business needs.

## 📚 Key Findings

### Algorithm Behavior
- **K-Means** forces spherical structures and minimizes inertia
- **DBSCAN** identifies natural density-based groupings
- **More clusters with DBSCAN** indicate fragmented natural patterns

### Business Impact
- **Hot zones identification** for optimal vehicle positioning
- **Temporal patterns** for dynamic resource allocation
- **Demand prediction** capabilities for operational efficiency

## 🚀 Getting Started

1. **Set up environment** with required libraries
2. **Load and merge** the 6 months of Uber data
3. **Create temporal features** and geographic samples
4. **Run clustering algorithms** with optimal parameters
5. **Generate visualizations** and compare results
6. **Apply insights** to operational strategies

---

## 👤 Author

Project by **Andriana**  
🔗 GitHub: [https://github.com/Andrianiniaina/0-Machine-Learning-Projects]
