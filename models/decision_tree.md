# Decision Trees: Understanding Entropy, Information Gain, and Feature Selection

This guide explains the concepts of **Entropy**, **Information Gain**, and how they are used in **Decision Trees** for classification problems.

---

## What is a Decision Tree?

A **Decision Tree** is a supervised machine learning algorithm used for both **classification** and **regression** tasks. The goal of a Decision Tree is to **split the data** into smaller and smaller groups, based on certain feature values, to help make predictions about the target variable.

### **How does a Decision Tree work?**

1. **Root Node**: The root node of the tree represents the entire dataset. It asks a question about one feature in the dataset.
  
2. **Splitting**: Based on the answer to the question, the dataset is divided into subsets. Each subset corresponds to one of the possible answers to the question (for example, "Humidity = High" or "Humidity = Low").
  
3. **Decision Nodes**: Each of these subsets can be further split using other features. These nodes are known as **decision nodes**, and they ask further questions to divide the dataset.

4. **Leaf Nodes**: Eventually, the tree reaches leaf nodes, where no further splitting can be done. These nodes represent the final prediction. For **classification** tasks, each leaf node represents a class label (e.g., "Yes" or "No"). For **regression** tasks, the leaf node contains a predicted value.

### **How are splits made?**

At each decision node, the **best feature** is chosen to split the dataset. This is done using metrics like **Information Gain**, **Gini Impurity**, or **Mean Squared Error** (depending on whether it's classification or regression). The goal is to pick the feature that results in the **purest** subsets—i.e., subsets where the target variable is as homogenous as possible.

---

## 1. What is Entropy?

### **Entropy of the Target Variable**

In Decision Trees, **Entropy** is used to measure the uncertainty or impurity of a dataset. Specifically, it measures how mixed the classes in the target variable are. If all the data points belong to the same class, the entropy is 0, meaning there's no uncertainty. If the data is evenly split between classes, the entropy is high, representing maximum uncertainty.

- **Example**:  (refer IBM)
  If the target variable is "Play Tennis" and the dataset has:
  - 9 days where "Play Tennis" is "Yes"  
  - 5 days where "Play Tennis" is "No"  
  - Then the initial entropy of the dataset will be calculated to understand how uncertain the target variable is.

The formula for entropy is:

$$ Entropy(S) = - ∑ p_i * log2(p_i) $$


Where `p_i` is the proportion of each class in the target variable.

---

## 2. Information Gain

### **What is Information Gain?**

**Information Gain** is a metric used to evaluate how much uncertainty (entropy) is reduced when we split the dataset based on a particular feature. The feature that provides the highest **Information Gain** is selected for splitting the data at each step.

The formula for **Information Gain** is:

$$ Gain(Tennis, A) = Entropy(Tennis) - ∑ ( |D_v| / |D| ) * Entropy(D_v) $$


Where:
- **Entropy(Tennis)**: The initial entropy of the target variable (before the split).
- **D_v**: The subset of data where the feature `A` has a particular value `v` (e.g., **Humidity = high** or **Humidity = normal**).
- **|D_v| / |D|**: The proportion of the data where the feature has the value `v`.

### **Why Calculate Information Gain?**

We calculate **Information Gain** for each feature to see which feature will give us the **best split** by reducing the **entropy** of the target variable the most. The feature with the highest **Information Gain** will be chosen to split the data at the current node of the decision tree.

---

## 3. Decision Tree Process: Recap

### **Step-by-Step Process**:

1. **Calculate the entropy of the target variable** (before any splits). This represents the **uncertainty** in the dataset.
   
2. **For each feature**, calculate the **Information Gain**. This tells us how much uncertainty (entropy) is reduced when the data is split by that feature.

3. The feature with the **highest Information Gain** (the greatest reduction in entropy) is chosen to **split the data** at the **current node**.

4. **Repeat the process** for each child node:
   - For each resulting subgroup (split), calculate the entropy of the target.
   - Calculate the Information Gain for each feature and select the one with the highest gain.
   - Continue splitting the data recursively until:
     - No further splits are possible (either all data points belong to the same class or other stopping conditions are met).

---

## 4. Simplified Example

Let's take a simple example where the target variable is **"Play Tennis"** and the features are **"Outlook"**, **"Humidity"**, and **"Temperature"**.

- **Step 1**: Calculate the **entropy of the target** (Play Tennis).
  - Let's say the entropy is **0.94**, indicating moderate uncertainty because we have a mix of **Yes** and **No** values.

- **Step 2**: For each feature, calculate the **Information Gain**.
  - For example, splitting the data based on **Humidity** (High vs Normal):
    - **High Humidity**: 7 samples, with entropy = 0.98.
    - **Normal Humidity**: 7 samples, with entropy = 0.59.
    - **Information Gain** for Humidity is calculated by measuring how much uncertainty is reduced after the split.

- **Step 3**: Repeat for other features like **Outlook** (Sunny, Overcast, Rainy).
  - The feature that gives the **highest Information Gain** is selected for the split at the root of the tree.

---

## 5. Key Points:

- **Entropy** tells us how **uncertain** the target variable is. Higher entropy means more mixed classes, and lower entropy means more pure (less uncertain) classes.
  
- **Information Gain** is used to **choose the best feature** for splitting the data. It measures how much **entropy** (uncertainty) is reduced by splitting based on a particular feature.

- The feature that provides the **highest Information Gain** is selected for the first split, and the process is repeated recursively for each child node until no further splits are possible.

---

## 6. Conclusion

By using **Entropy** and **Information Gain**, Decision Trees are able to intelligently split the data at each node, choosing the best features to classify the data and make predictions. The goal is to reduce uncertainty at each step, resulting in a model that is both efficient and easy to interpret.

---


