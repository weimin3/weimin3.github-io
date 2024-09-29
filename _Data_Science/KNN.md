# How it works?

1. Determine K: Choose the number of neighbors (K). The optimal K is typically found through cross-validation
- Small K: A small value of K (e.g., 1 or 3) makes the model **sensitive to noise** in the data, as it only considers the closest neighbors, which could be outliers.
- Large K: A large value of K makes the decision boundary smoother but can lead to a model that is too simple, potentially **underfitting the data**.
2. Calculate Distance: For a new data point (query point), calculate the distance between this point and all points in the training dataset. Common distance metrics include:
- Euclidean Distance: Most commonly used. Given two points $$P = (x_1, y_1)$$ and $$Q = (x_2, y_2)$$ is：
$$
d(P, Q) = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}
$$
- Manhattan Distance: Sum of the absolute differences of their coordinates.
- Minkowski Distance: A generalization of Euclidean and Manhattan distances.
3. Find Neighbors: Identify the K closest data points in the training set to the query point.
4. Majority Vote(For Classification): The class label of the query point is determined by the majority class among its K nearest neighbors. For instance, if 3 out of 5 neighbors are labeled "positive" and 2 are labeled "negative," the query point is classified as "positive." 
5. Average or Weighted Average(For Regression): The prediction for the query point is typically the average of the values of its K nearest neighbors. In some cases, a weighted average might be used, where closer neighbors have more influence.

****


[Back to Introduction to Machine Learning](machine_learning.md)