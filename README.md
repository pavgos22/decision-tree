# Decision Tree and Random Forest Implementation

This project contains an implementation of Decision Tree and Random Forest algorithms, applied to the Titanic dataset. The purpose is to build predictive models to determine the likelihood of survival of passengers on the Titanic, based on various features.

## Project Structure

- **Node Class (`node.py`)**: Represents a single node in the decision tree. It contains methods to:
  - Calculate the best split of the data using the Gini impurity criterion.
  - Split data into left and right child nodes.
  - Predict the outcome for new data points.

- **DecisionTree Class (`decision_tree.py`)**: Represents the decision tree algorithm. It includes methods to:
  - Train the decision tree on the training dataset.
  - Predict outcomes for new data points.
  - Evaluate the model's performance using accuracy.

- **RandomForest Class (`random_forest.py`)**: Represents the random forest algorithm, which is an ensemble of decision trees. It includes methods to:
  - Train multiple decision trees on different subsets of the training data (using bagging).
  - Aggregate the predictions from all trees to make a final prediction.
  - Evaluate the model's performance using accuracy.

- **Helper Functions (`load_data.py`)**:
  - `generate_data()`: Generates random synthetic data for training and testing.
  - `load_titanic()`: Loads and preprocesses the Titanic dataset from a CSV file, preparing it for use with the decision tree and random forest models.

- **Main Script (`main.py`)**: The entry point of the project that:
  - Loads the Titanic dataset.
  - Trains both a decision tree and a random forest model on the data.
  - Evaluates the performance of both models on the training and test datasets.

## How It Works

1. **Decision Tree**:
   - The algorithm begins at the root of the tree, analyzing the entire training dataset to find the best possible split based on the Gini impurity criterion.
   - Data is split into two subsets, and the process is recursively repeated for each child node until the maximum tree depth is reached or no further splits are possible.

2. **Random Forest**:
   - The algorithm creates multiple decision trees, each trained on a different subset of the training data using the bagging technique (sampling with replacement).
   - At each split in the trees, only a random subset of features is considered to ensure diversity among the trees.
   - Predictions from all trees are averaged to make a final prediction, improving model stability and reducing the risk of overfitting.

