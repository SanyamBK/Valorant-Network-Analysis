---
title: "Structural Topology and Survivorship Bias in E-Sports: A Network Science Analysis"
author: "Group 47"
date: "April 2026"
---

# Slide 1: Title
**Title:** Structural Topology and Survivorship Bias in E-Sports: A Network Science Analysis of Professional Valorant Matches  
**Presenters:** Group 47  
**Course:** Network Science  
**Topic:** Leveraging Complex Graphs to Measure Team Cohesion and Predict Match Outcomes  

*[DESIGN SUGGESTION: Place a professional Valorant VCT (Valorant Champions Tour) logo or an abstract network graph stock image faintly in the background here.]*

---

# Slide 2: Introduction
### Defining the Problem Space
* E-Sports features massive player fluidity, frequent substitutions, and dynamic roster formations.
* Tabular stat-tracking (Kills, Deaths, Assists) fails to quantify long-term competitive "cohesion."
* **Our Approach:** Treat professional matches as a complex social graph to isolate the underlying strategic architecture of the competitive ecosystem.
* **Goal:** Fulfill 4 key deliverables (Graphing, Metric Extraction, Communities, Predictive Modeling) strictly via network structure.

*[DESIGN SUGGESTION: Include a split-screen or side-by-side graphic showing a traditional scoreboard KDA stat-line vs a highly interconnected glowing node network.]*

---

# Slide 3: Deliverable 1 - Graph Construction
### Building the Interaction Network
* **Dataset:** 24,947 validated professional Valorant matches globally (April 2021+).
* **Nodes ($V$):** 8,793 unique professional players.
* **Edges ($E$):** 236,225 unique "co-play" relationships.
* **Semantic Weighting:** The edge weight between Player A and Player B increases monotonically for every official match they play together, proxying deeply entrenched team synergy.

*[INSERT TABLE SUGGESTION: A small 3-row, 3-column table showing the schema of our graph (Node = Player Name, Edge = Co-Existence, Weight = Matches Played Together).]*

---

# Slide 4: Deliverable 2 - Network Analytics & Topologies
### Centralities and Distributions
* **Heavy-Tail Right Skew:** Massive clusters of rookie/amateur players exist loosely connected at the bottom, while veteran players act as "anchor pillars".
* **Centrality Markers:** PageRank and Eigenvector Centrality strongly correlate, identifying players who consistently compete alongside other highly successful players.

*[INSERT IMAGE HERE: Place `results/plots/degree_distribution.png` prominently on the right side of this slide to visualize the heavy tail!]*

*[INSERT SECOND IMAGE: Below it, or on the next slide, showcase `results/plots/centrality_comparison.png` to map out the PageRanks.]*

---

# Slide 5: The Math Anomaly - Survivorship Bias
### Uncovering the "Zero-Sum" Violation
* **Observation:** The unweighted global mean win rate for players crashed to ~28%, violating the mathematical law that an adversarial game average must be exactly 50%.
* **The Culprit:** Tournament brackets natively suffer from **Survivorship Bias**. Thousands of amateur teams play exactly 1 match in a qualifier and drop out forever with a 0% win rate.
* **The Solution:** We corrected this using the **True Weighted Win Rate**, instantly shifting the graph's analytics back to structurally balanced zero-sum integrity.

*[DESIGN SUGGESTION: This is a complex slide. Use a simple, punchy schematic showing 1 Pro (Winning 500 Matches) vs 500 Amateurs (Losing 1 Match and eliminated) to visually explain Survivorship Bias.]*

---

# Slide 6: Deliverable 3 - Community Detection
### Partitioning Functional Ecosystems
* Executed the **Louvain Modularity Method ($Q$)** to mathematically partition the 8,793 players.
* **Result:** Discovered exactly **27 Active Communities** operating cohesively.
* **Insight:** Applying our True Weighted Win Rate, we found certain hyper-dense regional subsets mathematically possess consistent sub-percent advantages (50.5%+) over other global communities.

*[INSERT IMAGE HERE: Prominently place the `results/plots/community_win_rates.png` bar chart directly in the center to highlight the micro-advantages oscillating cleanly around the 50% baseline.]*

---

# Slide 7: Deliverable 4 - Machine Learning Match Predictor
### Forecasting Purely from Topology
* Can we predict who will win a random match strictly by looking at their graph structure (ignoring all mechanical skills or game-agents)?
* **Feature Engineering:** We calculated aggregate relative differentials in *Degree* and *PageRank* between `Team 1` and `Team 2`.
* **Testing & Validation (80/20 Split):** Let the models predict binary outcomes.

*[INSERT IMAGE HERE: Insert the `results/plots/confusion_matrix.png` heat-map on the right to visualize the True Positives & False Positives of our Random Forest testing split.]*

---

# Slide 8: Machine Learning Results
### Algorithm Performance
* **Logistic Regression:** 65.68% Accuracy
* **Random Forest Classifier:** **66.84% Accuracy**
* **Conclusion:** The massive 67% accuracy explicitly proves our hypothesis: high-density interaction structure and high network centrality are direct, irrefutable proxies for competitive dominance and roster stability.

*[DESIGN SUGGESTION: Put "66.84% Accuracy" in giant, bold text or a visually distinct call-out box to emphasize that Graph Centralities alone predicted 2/3rds of all highly volatile matches.]*

---

# Slide 9: Thank You & Q/A
Let's open the floor to any questions regarding preprocessing, centrality engineering, Louvain clustering, or random forest hyperparameters!

*[DESIGN SUGGESTION: Final slide stock image - maybe a dark e-sports stadium stage with stage lights or a "GG" (Good Game) neon typography.]*
