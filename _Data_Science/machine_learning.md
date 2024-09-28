---
# title: "Machine Learning"
collection: Data_Science
permalink: /Data_Science/machine_learning/
---
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

### Logistic Regression

### Decision Trees

### Random Forest

### Support Vector Machines(SVM)


### K-Nearest Neighbors(KNN)
KNN classifies a data point based on the majority label of its nearest neighbors in the feature space. For regression, the prediction is the average of the nearest neighbors.

**Task:** Both Classification and Regression

  
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

### Hierarchical Clustering

### Principal Component Analysis(PCA)

### Autoencoders

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

### Deep Q-Networks(DQN)

### Policy Gradient Methods


## Application
- Robotics
- Game AI
- Autonomous Vehicles
