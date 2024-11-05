# NAVIGATELABSAI Assignment-1: Decision Tree in Machine Learning

## Table of Contents
- [Overview](#overview)
- [Introduction to Decision Trees](#introduction-to-decision-trees)
- [Key Concepts and Terminology](#key-concepts-and-terminology)
- [Steps in Building a Decision Tree](#steps-in-building-a-decision-tree)
- [Advantages and Limitations](#advantages-and-limitations)
- [Practical Applications](#practical-applications)
- [Code Implementation](#code-implementation)
- [Results](#results)
- [Contributors](#contributors)
- [Conclusion](#conclusion)

## Overview
This project demonstrates a decision tree model for classification tasks in machine learning. Decision trees simplify complex decision-making by breaking down decisions into a series of simpler choices. This repository contains code to build, visualize, and evaluate a decision tree on a sample dataset.

## Introduction to Decision Trees
Decision trees are a popular supervised learning algorithm for both classification and regression. They are structured as a branching tree, where:
- **Root Node**: The starting point of the tree.
- **Internal Nodes**: Represent decisions based on specific attributes.
- **Branches**: Show possible outcomes of each decision.
- **Leaf Nodes**: Deliver the final classification or prediction.

Decision trees are valued for their interpretability, making them ideal for fields like medical diagnosis, finance, and customer segmentation.

## Key Concepts and Terminology
- **Root Node**: The starting point of the tree.
- **Internal Node**: A decision point based on an attribute.
- **Leaf Node**: Represents the final classification or prediction.
- **Branch**: A possible outcome of a decision node.
- **Decision Boundary**: The line that separates different classifications.

## Steps in Building a Decision Tree
1. **Data Preparation**: Clean and pre-process the data for optimal training.
2. **Attribute Selection**: Select the best attribute to split data at each node.
3. **Tree Growth**: Recursively split data until a stopping criterion is met.
4. **Pruning**: Simplify the tree to prevent overfitting.

## Advantages and Limitations
### Advantages
- **Interpretability**: Decision trees are easy to understand and visualize.
- **Non-Parametric**: Can handle both categorical and numerical data.
- **Robustness**: Relatively resistant to outliers and noisy data.

### Limitations
- **Overfitting**: Trees can become too complex, leading to poor generalization.
- **Instability**: Small data changes can significantly affect the tree.
- **Bias**: May be biased toward attributes with more categories.

## Practical Applications
- **Medical Diagnosis**: Predict diseases and treatments based on symptoms.
- **Financial Risk Assessment**: Evaluate creditworthiness and loan defaults.
- **Customer Segmentation**: Group customers by preferences and behaviors.
- **Machine Learning Automation**: Apply to tasks like fraud detection and image classification.

## Code Implementation

### Libraries Used
- `pandas`: For data manipulation.
- `sklearn.tree`: For building and visualizing the decision tree.
- `matplotlib`: For plotting the decision tree.

### Dataset
A sample dataset with attributes `a1`, `a2`, `a3`, and `Classification` is used for training and testing the decision tree model.

### Example Code
```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier
from sklearn import tree
import matplotlib.pyplot as plt

# Create the dataset
data = {
    'a1': [True, True, False, False, False, True, True, True, False, False],
    'a2': ['Hot', 'Hot', 'Hot', 'Cool', 'Cool', 'Cool', 'Hot', 'Hot', 'Cool', 'Cool'],
    'a3': ['High', 'High', 'High', 'Normal', 'Normal', 'High', 'High', 'Normal', 'Normal', 'High'],
    'Classification': ['No', 'No', 'Yes', 'Yes', 'Yes', 'No', 'No', 'Yes', 'Yes', 'Yes']
}
df = pd.DataFrame(data)
df_encoded = pd.get_dummies(df[['a1', 'a2', 'a3']])
df['Classification'] = df['Classification'].map({'Yes': 1, 'No': 0})

X = df_encoded
y = df['Classification']

# Train Decision Tree
clf = DecisionTreeClassifier(criterion='entropy')
clf.fit(X, y)

# Visualize the Decision Tree
plt.figure(figsize=(12,8))
tree.plot_tree(clf, feature_names=X.columns, class_names=['No', 'Yes'], filled=True)
plt.show()

# Predict and Evaluate
y_pred = clf.predict(X)
accuracy = (y_pred == y).mean()
print(f"Accuracy: {accuracy * 100:.2f}%")
# Machine Learning Project 🤖

## Results 📊
The decision tree model achieved an accuracy of 100% on the training dataset, demonstrating that it correctly classified all instances. However, this may indicate overfitting, suggesting that further evaluation on a test set is recommended.

## Contributors ✨
<table>
 <tr>
   <td align="center">
     <a href="#">
       <br />
       <sub><b>Sarankumar S.</b></sub>
       <br />
       <sub>22AM055</sub>
     </a>
   </td>
   <td align="center">
     <a href="#">
       <br />
       <sub><b>Ajinesh</b></sub>
       <br />
       <sub>22AM007</sub>
     </a>
   </td>
   <td align="center">
     <a href="#">
       <br />
       <sub><b>Gobika</b></sub>
       <br />
       <sub>22AM069</sub>
     </a>
   </td>
 </tr>
</table>

## License 📝
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

---
⭐ Star this repository if you find it helpful!
