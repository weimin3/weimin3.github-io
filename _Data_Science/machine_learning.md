---
title: "Machine Learning"
collection: Data_Science
permalink: /Data_Science/machine_learning/
---
- [Supervised Learning](#supervised-learning)
  - [Key Characteristics](#key-characteristics)
  - [Common algorithms](#common-algorithms)
    - [Linear Regression](#linear-regression)
    - [Logistic Regression](#logistic-regression)
    - [Decision Trees](#decision-trees)
    - [Random Forest](#random-forest)
    - [Support Vector Machines(SVM)](#support-vector-machinessvm)
    - [K-Nearest Neighbors(KNN)](#k-nearest-neighborsknn)
  - [Applications](#applications)
- [Unsupervised Learning](#unsupervised-learning)
  - [Key Characteristics](#key-characteristics-1)
  - [Common algorithms](#common-algorithms-1)
    - [K-Means Clustering](#k-means-clustering)
    - [Hierarchical Clustering](#hierarchical-clustering)
    - [Principal Component Analysis(PCA)](#principal-component-analysispca)
    - [Autoencoders](#autoencoders)
  - [Application](#application)
- [Reinforcement Learning](#reinforcement-learning)
  - [Key Characteristics](#key-characteristics-2)
  - [Common algorithms](#common-algorithms-2)
    - [Q-Learning](#q-learning)
    - [Deep Q-Networks(DQN)](#deep-q-networksdqn)
    - [Policy Gradient Methods](#policy-gradient-methods)
  - [Application](#application-1)
- [Types of Tasks](#types-of-tasks)


Machine Learning(ML) is a branch of Artificial Intelligence(AI) that allows computers to learn from data without being explicitly programmed. Instead of following hardcoded instructions,ML use patterns and inference to make predictions or decisions,improving their performance over time.

Machine learning is categorized into three main types:supervised learning,unsupervised learning and reinforcement learning.

# Supervised Learning
In supervised learning, the algorithm is trained on a labeled dataset, which means the input data(features) is paired with the correct output(labels).
## Key Characteristics
- Labeled data: Each training example consists of input-output pairs
- Goal: Learn a mapping from inputs to outputs to make predictions on new,unseen data.
- Common problems: Classification (categorizing) and regression (predicting continuous values)

## Common algorithms
### Linear Regression
Predicts a continuous target value based on linear relationships between the input features (independent variables) and the target variable (dependent variable).

**Task:** Regression

**Use Case:** Predicting house prices based on square footage, number of bedrooms, etc.

### Logistic Regression
Despite the name, logistic regression is used for **binary classification problems**. It models the probability that a given input belongs to a particular class (e.g., 0 or 1) using a logistic function.

**Task:** Classification

**Use Case:** Spam detection, where emails are classified as either spam or not spam.

### Decision Trees
A tree-like structure where each internal node represents a feature, each branch represents a decision rule, and each leaf represents an outcome.

**Task:** Both Classification and Regression

**Use Case:** Predicting whether a customer will buy a product (classification) or predicting the value of a car (regression).

### Random Forest
An ensemble of decision trees, where each tree is trained on a random subset of the data. The final prediction is made by averaging (regression) or voting (classification) across all the trees.

**Task:** Both Classification and Regression

**Use Case:** Predicting loan default risk (classification) or house price prediction (regression).

### Support Vector Machines(SVM)
SVM finds the hyperplane that best separates the classes in the feature space. In cases where the data is not linearly separable, it uses a kernel trick to map data into higher dimensions.

**Task:** Mostly Classification

**Use Case:** Image classification (e.g., distinguishing cats from dogs in images)


### K-Nearest Neighbors(KNN)
KNN classifies a data point based on the majority label of its nearest neighbors in the feature space. 
For regression, the prediction is the average of the nearest neighbors.

**Task:** Both Classification and Regression

**Use Case:** Predicting the rating of a movie (regression) or classifying a plant species based on its features (classification).

  
## Applications
- Image Classification
- Spam Detection
- Predictive Analytics


# Unsupervised Learning
In unsupervised learning,the algorithm works with unlabeled data.The model is tasked with finding hidden patterns,relationships or structures in the data without explicit guidance.
## Key Characteristics
- Unlabeled data: The dataset contains input data without corresponding output labels.
- Goal: Discover hidden patterns,groupings, or relationships in the data.
- Common Problems:Clustering(grouping similar data points) and dimensionality reduction(simplifying data while retaining its structure)

## Common algorithms
### K-Means Clustering
This algorithm partitions data points into K clusters based on similarity. Each data point is assigned to the nearest cluster centroid, and the centroids are updated iteratively.

**Task:** Clustering 

**Use Case:** Customer segmentation based on purchase behavior

### Hierarchical Clustering
A tree-like structure of clusters is built by either merging small clusters into bigger ones (agglomerative) or splitting big clusters into smaller ones (divisive).

**Task:** Clustering

**Use Case:** Grouping similar documents together for topic modeling.


### Principal Component Analysis(PCA)
PCA transforms the data into a lower-dimensional space by identifying the most important features that capture the most variance in the data.

**Task:** Dimensionality Reduction

**Use Case:** Reducing the number of variables in image compression.

### Autoencoders
A type of neural network that learns to encode the input into a compressed representation and then reconstruct the input from this reduced encoding. Used in unsupervised settings for tasks like anomaly detection.

**Task:** Dimensionality Reduction or Feature Learning

**Use Case:** Detecting fraudulent transactions by identifying patterns that deviate from the norm.

## Application
- Market Segmentation
- Anomaly Detection
- Recommender Systems

# Reinforcement Learning
Reinforement learning(RL) involves an agent interacting with an environment,learning to make decisions through trial and error.
The agent receives feedback in the form of rewards or penalties and aims to maximaze the cumulative reward over time.
## Key Characteristics
- Agent-Environment Interaction: The agent takes actions in an environment and observes the results.
- Goal: Learn an optimal strategy (policy) to maximize long-term rewards.
- Exploration vs. Exploitation: The agent must balance exploring new actions (to learn more) and exploiting known actions (to maximize rewards).

## Common algorithms
### Q-Learning
Q-learning is a model-free reinforcement learning algorithm that learns a value function to predict the expected utility of taking a certain action in a certain state.

**Task:** Decision Making

**Use Case:** Game-playing agents like AlphaGo, which learn strategies to win.

### Deep Q-Networks(DQN)
Combines Q-learning with deep neural networks to approximate the Q-values for large and complex environments.

**Task:** Decision Making

**Use Case:** Self-driving cars

### Policy Gradient Methods
Instead of learning a value function, policy gradient methods directly learn the optimal policy, which defines the best action to take in each state.

**Task:** Decision Making

**Use Case:** Robotics control

## Application
- Robotics
- Game AI
- Autonomous Vehicles

# Types of Tasks
- Classification: Assigning an input to a category (e.g., spam vs. not spam).
- Regression: Predicting a continuous value (e.g., house prices, stock market trends).
- Clustering: Grouping similar data points together (e.g., customer segmentation).
- Dimensionality Reduction: Reducing the number of features while retaining important information (e.g., data compression).
- Decision Making: Learning to take actions to maximize rewards (e.g., in games or autonomous systems).
