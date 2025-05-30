# Search Tree Experimental Performance Comparison

This project consists of an experimental comparison of Balancing Search Trees. To do this, I have developed an experimental framework which evaluates the insertion and performance of three data structures:
- AVL Tree
- Left-Leaning Red-Black Tree
- Scapegoat Tree

## Motivation

Many proposed solutions to the problem of building balanced search trees, even with completely different approaches, have exactly the samae space and time complexity. This is the case for the following three trees:
- AVL Tree (Space, O(n); Time, O(log n))
- Left-Leaning Red-Black Tree (Space, O(n); Time, O(log n))
- Scapegoat Tree (Space, O(n); Time, O(log n))
The aim of this experiment is therefore to experimentally study the practical performace of the different data structures and identify under which circumstances it is better to use one or the other.

## Data Structure Implementation

The data structures have all been implemented in Python. There is a parent class, AbstractSearchTree, which supports both insert and search operations. This will be useful as it ensures that the testing framework only needs to be written once and can be reusable for the three data structures.

## Algorithm Evaluation

### Data Generation

I have developed a TestDataGenerator which creates seven types of datasets:
- Random
- Sorted Ascending
- Sorted Descending
- Almost Sorted
- Alternating
- Only Duplicates
- Half Duplicates
This will ensure that all data structures are tested under many circumstances and will provide evidence to decide which data structures are more suitable under different conditions of the input data.

### Statistical Analysis

For each dataset, the framework runs muultiple trials of each test for accuracy. Insertion and search times are calculated and plotted on cumulative box plots to show how they differ across different data distributions and algorithms. Line graphs are used to track performance trends as the dataset size increases.

Given that the distributions are not necessarily normal, I have used the following non-parametric statistical tests:
- Kruskal-Wallis Test, used to determine if any dataset type performs in significantly different way.
- Dunn's Test, used to compare the dataset types pairwise, and identify which specific dataset differst in performance.

### Hardware Setup

The results evaluated in the report come from tests frun on a MacBook Air (2024) with Apple M3 Chip and 16GB of RAM.

The datasets run have the following sizes: 10, 50, 100, 500, 1000, 2500, 5000, 10000 elements.

### Results

The performance results and analysis can be found in the Report.
