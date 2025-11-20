# FIFA-ML-RECOMMENDER
A machine learning system for recommending statistically similar football players using K-Means clustering and Euclidean Distance.

⚽ FIFA ML Player Recommendation Engine:
A data science project built to provide optimal, data-driven replacement recommendations for professional football clubs by matching a target player's statistical profile with the most similar available candidates, filtered by strict business constraints (Age and Affordability).

🎯 Project Goal:
The primary objective is to solve the complex problem of player replacement scouting by replacing human intuition with a robust, scalable Machine Learning approach.
Given a player who is retiring or injured, the engine identifies players who:
1. Share the exact same playing style (archetype).
2. Are the closest statistical match in skill attributes (Pace, Finishing, Defense, etc.).
3. Are Affordable (within a defined wage budget).

🧠 Methodology-Unsupervised Learning (K-Means & Euclidean Distance):
1. Data Preparation & Feature Scaling Action:
All individual skill attributes (Pace, Finishing, Defense, Potential, etc.) and market values are Standardized using StandardScaler.
Concept: Scaling ensures that no single feature (like a high Market Value number) unfairly dominates the distance calculation, forcing the model to rely purely     on the relative shape of the player's profile.
2. Player Archetype Clustering Algorithm:
K-Means Clustering was applied to the standardized feature set.
Optimal K: The Elbow Method determined that the optimal number of distinct player archetypes is k=6.
Output: Every player in the database is assigned a Cluster_ID (Archetype). This pre-filtering step ensures that, for instance, a Center Back (CB) is never compared to a Striker (ST).
3. Similarity Scoring (Euclidean Distance) Metric: Euclidean Distance is calculated between the target player and all candidate players within the same  Cluster_ID.Concept: Euclidean Distance measures the geometric straight-line distance between two points in the multi-dimensional feature space. A lower distance signifies higher statistical similarity between the two player profiles.

💻 Technical Stack:
Language: Python
Libraries: Pandas, NumPy, Scikit-learn (for K-Means and distance metrics)
Interface: ipywidgets (for the interactive player selection input), IPython.
