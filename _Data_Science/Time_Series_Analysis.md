---
title: "Time Series Analysis"
collection: Data_Science
permalink: /Data_Science/Time_Series_Analysis/
---
Time series analysis is a statistical technique that deal with time-ordered data points.Time series data refers to a sequence of observations taken at successive points in time，often uniform intervals.(e.g., daily stock price,monthly sales figures,etc.)

**Types of time series:**
- Univariate time series: a single variable is recorded over time.(e.g., daily temperatures)
- Multivariate time series: multiple variables are recorded over time.

**Key components of time series:**
- Trend: the long-term upward or downward direction of the data.
- Seasonality: regular,repeating fluctuations in the data,often tied to specific times of the year,week, or day.
- Cyclic Patterns: Longer-term oscillations that are not of fixed duration.

# Time series clustering
Time series clustering involves grouping time series data based on similarity patterns.

Time series clustering involves two main types:subsequence clustering and time point clustering.

1. Subsequence clustering: using a sliding window approach to extract segments(subsequences) from a longer time series.there subsequences are then clustered based on their similarity.

2. Time point clustering: clustering is based on the proximity of time points and the similarity of their corresponding values.

## Similarity Measures
1. Dynamic time warping(DTW):aligns two time series that may vary in speed or length.It warps the time axis to minimize the distance between corresponding points in two seires. it is commonly used for speech recognition and financial time series analysis.  
   
```Python
from scipy.spatial.distance import euclidean
from fastdtw import fastdtw

x = [1, 2, 3, 4, 5]
y = [1, 2, 2, 4, 4, 5]

# DTW using fastdtw
distance, path = fastdtw(x, y, dist=euclidean)
print("DTW Distance: ", distance)
print("Path: ", path)
```
Output:
```python
DTW Distance: 1.0
Path: [(0, 0), (1, 1), (2, 2), (3, 3), (4, 4), (4, 5)]
```
It means the total distance after alignment is 1.0, and the optimal alignment (warping) occurs according to the shown pairs of indices.

2. Euclidean Distance:calculating the straight-line distance between corresponding points in two equally sized time series.It works best when both series have the same length and no time-shift differences, such as sensor data in controlled environments.
```python
import numpy as np

x = np.array([1, 2, 3, 4, 5])
y = np.array([1, 2, 2, 4, 5])

# Euclidean distance between two time series
distance = np.linalg.norm(x - y)
print("Euclidean Distance: ", distance)
```
Output:
```python
Euclidean Distance: 1.0
```
3. Correlation-based Metrics:Correlation measures the similarity in the shape or trend between two time series, regardless of the magnitude. A common example is the Pearson correlation.It is useful when we care more about the trend or pattern in the data (e.g., stock market analysis).
   
```python
import numpy as np
from scipy.stats import pearsonr

x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 4, 6, 8, 10])

# Pearson correlation coefficient
correlation, _ = pearsonr(x, y)
print("Pearson Correlation: ", correlation)
```
Output:
```python
Pearson Correlation: 1.0
```
## Clustering methods
1. K-Means:partitions time series into k clusters based on distance metrics.The distance between time series is typically measured using Euclidean distance or DTW.
   

2. K-Shape: A variant that uses shape-based distance to improve clustering for time series.It uses shape-based distance (a form of normalized cross-correlation) to help capture the shape of time series rather than their values.
   
3. Hierarchical Clustering:Builds a tree-like structure to visualize and analyze the clustering process.