# MSCS 634 – Lab 5: Hierarchical and DBSCAN Clustering

**Student:** Rajasekhar Reddy Kayyam  
**Course:** MSCS 634 – Advanced Big Data and Data Mining

## Purpose
Explore and compare Ward Agglomerative Hierarchical Clustering and DBSCAN on the scikit-learn Wine dataset (178 observations, 13 numeric chemical features). Standardize features, visualize clusters with 2D PCA, inspect a dendrogram, and evaluate silhouette, homogeneity, and completeness.

## Files
- `MSCS_634_Lab_5.ipynb` — complete executed notebook with code, tables, figures, and interpretation.

## How to run
```bash
python -m pip install numpy pandas matplotlib seaborn scikit-learn scipy notebook
jupyter notebook MSCS_634_Lab_5.ipynb
```
Run all cells from top to bottom.

## Key insights
- Hierarchical clustering assigns all samples to clusters; varying `n_clusters` between 2, 3, and 4 changes group granularity. The Ward dendrogram displays how groups merge at different linkage distances.
- DBSCAN is sensitive to `eps` and `min_samples`; tighter neighborhoods typically label more observations as noise, while looser neighborhoods can merge groups.
- Scores capture different properties: silhouette evaluates geometry; homogeneity and completeness compare against the dataset's known wine classes (used only for evaluation).
- DBSCAN noise is explicitly shown as black X marks. The notebook treats noise as a separate label when computing all-point scores and marks silhouette as unavailable when mathematically undefined. A high score must be considered alongside cluster count and noise fraction.

## Decisions and challenges
- Standardized all 13 features because the chemical measurements have different scales.
- Used PCA **only** to display 2D plots; algorithms and silhouette use all standardized features.
- Tested a small grid of DBSCAN settings rather than assuming one parameter combination would work.
- Accounted for configurations that produce no meaningful clusters or undefined silhouette scores.

## Submission
Create a public GitHub repository named `MSCS_634_Lab_5`, upload both files, and submit its URL to the instructor.
"# MSCS_634_Lab_5" 
