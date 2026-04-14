# Player Interaction Network Analysis in Valorant

## 1. Introduction
This report summarizes the construction and analysis of a player interaction network using the **Valorant Pro Matches Dataset**. The goal was to extract actionable insights from player interaction structures and predict match outcomes.

## 2. Methodology

### Data Preprocessing
We processed `data-since-april-2021.csv`, generating a dataset of 24,947 matches. Players were constructed as nodes, and edges were added between players co-existing in the same matches.

### Deliverable 1: Graph Construction
* **Nodes**: 8,793 unique professional players
* **Edges**: 236,225
* **Edge Semantics**: Weight represents the number of co-played matches.

### Deliverable 2: Network Analysis
* **Degree Distribution**: The distribution showcases a long tail, indicating that a few veteran players have played alongside a massive number of distinct players, while rookies are fairly isolated.
* **Centrality**: Eigenvector Centrality and PageRank were highly correlated, singling out key anchor players in the competitive scene.

### Deliverable 3: Community Detection
* **Louvain Algorithm**: We partitioned the graph into **27 active communities**.
* **Community Characteristics**: Several communities had significantly higher win rates than the 50% baseline, suggesting long-standing cohesive strategy groups across distinct e-sport organizations.

### Deliverable 4: Machine Learning Predictor
We transformed the predictive task to a binary classification problem: *Did Team 1 Win?*
* Features utilized: Differential Degree, PageRank, Clustering Coefficient, and Eigenvector Centrality between Team 1 and Team 2.
* **Logistical Regression Accuracy**: 65.68%
* **Random Forest Accuracy**: 66.84%
The strong predictive power solely derived from network structure proves that high-centrality, well-connected teams have a definitive structural advantage over loosely-connected player clusters.

## 3. High-Level Conclusions
Unlike previous simplistic implementations, this analysis strictly isolated match causality via purely structural network metrics, confirming that robustly connected players form highly successful functional communities.
