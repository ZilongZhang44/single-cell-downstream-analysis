# single-cell-downstream-analysis
## Critical downstream analysis steps for single-cell RNA sequencing data
### Clustering
[Seurat](https://satijalab.org/seurat/articles/install.html)：
By treating each cell as a node, a graph can be built by finding the k-nearest neighbour for each node. The edges in the graph represent the similarity relationships between the cells. The main drawback of this clustering algorithm used in Seurat is that the result is relatively sensitive to the parameter (resolution), and the default algorithm (Louvain method) may generate false clusters in some cases.

### Trajectory inference
### Cell type annotation
### Integrating dataset
