# Single-cell-downstream-analysis
## Critical downstream analysis steps for single-cell RNA sequencing data
### Clustering
[Seurat](https://satijalab.org/seurat/)：
As the most popular R package for single-cell sequencing data analysis pipeline, Seurat utilized Louvain method for clustering.<br>
[SCANPY](https://scanpy.readthedocs.io/en/stable/):
A python package also widely used for single-cell data analysis, which utilizes Louvain algorithm for clustering.<br>
[SC3](http://bioconductor.org/packages/release/bioc/html/SC3.html):
Performs k-means clustering several times with different initial values and obtains the consensus as the final result. In addition, k-means clustering is extremely sensitive to outlier cells.<br>
[RaceID](https://github.com/dgrun/RaceID):
Shows great performance in rare cell type identification. Hierarchical clustering tries to build a hierarchy of clusters using either a “bottom-up” or a “top-down” approach.<br>
[CIDR](https://github.com/VCCRI/CIDR):
Takes dropout events into consideration and performs hierarchical clustering after dimensionality reduction by principal coordinates analysis (PCoA).
[BackSPIN](https://github.com/linnarsson-lab/BackSPIN):
As an iterative dimension reduction and hierarchical clustering method based on SPIN, shows great improvement in identifying rare cell types.
### Trajectory inference
### Cell type annotation
### Integrating dataset
