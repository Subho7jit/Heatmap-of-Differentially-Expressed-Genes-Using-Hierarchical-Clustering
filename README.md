# Heatmap-of-Differentially-Expressed-Genes-Using-Hierarchical-Clustering
Description:
This R script processes gene expression data to create a heatmap of differentially expressed genes (DEGs) with hierarchical clustering applied to samples. It involves log transformation, distance calculation, clustering, and visualization using a color gradient from blue to red.

Steps Involved:
Load Required Library:

library(stats) → Loads the stats package for clustering functions.
Log Transformation of Gene Expression Data:

df_log = log2(df + 1) → Applies log2 transformation to stabilize variance and normalize the data.
Hierarchical Clustering of Samples:

df_dist = dist(t(df_log)) → Computes the distance matrix between samples based on log-transformed data.
df_hc = hclust(df_dist) → Performs hierarchical clustering on the distance matrix.
Heatmap Generation:

heatmap(df_log, Rowv = as.dendrogram(df_hc), Colv = FALSE, ...)
Visualizes the expression levels using a heatmap where:
Rows (genes) are clustered based on similarity.
Columns (samples) are not clustered (Colv = FALSE).
Color gradient (blue → white → red) represents low to high expression.
Labels for rows (labRow = group) represent gene groups.
Axis labels and title are customized for clarity.
