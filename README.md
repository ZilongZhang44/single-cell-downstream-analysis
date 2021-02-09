# Single-cell-downstream-analysis
## Critical downstream analysis steps for single-cell RNA sequencing data
### Pipeline for analysing scRNA-seq technology
The whole pipeline of scRNA-seq technology analysis is shown in Figure 1. Owing to the noisy character of scRNA-seq data, data processing steps are generally important; however, elaboration for this part of the analysis is beyond the scope of this review, and we recommend that readers refer to these articles for further information [21-24]. In this review, we focus on downstream analysis, including clustering, trajectory inference, cell type annotation and dataset integration. As shown in Figure 1, we divide popular methods into several categories for better discussion. In each section, we provide our perspectives for choosing proper tools in different situations.
### Clustering
* [Seurat](https://satijalab.org/seurat/):
As the most popular R package for single-cell sequencing data analysis pipeline, Seurat utilized Louvain method for clustering.<br>
[SCANPY](https://scanpy.readthedocs.io/en/stable/):
A python package also widely used for single-cell data analysis, which utilizes Louvain algorithm for clustering.<br>
[SC3](http://bioconductor.org/packages/release/bioc/html/SC3.html):
Performs k-means clustering several times with different initial values and obtains the consensus as the final result. In addition, k-means clustering is extremely sensitive to outlier cells.<br>
[RaceID](https://github.com/dgrun/RaceID):
Shows great performance in rare cell type identification. Hierarchical clustering tries to build a hierarchy of clusters using either a “bottom-up” or a “top-down” approach.<br>
[CIDR](https://github.com/VCCRI/CIDR):
Takes dropout events into consideration and performs hierarchical clustering after dimensionality reduction by principal coordinates analysis (PCoA).<br>
[BackSPIN](https://github.com/linnarsson-lab/BackSPIN):
As an iterative dimension reduction and hierarchical clustering method based on SPIN, shows great improvement in identifying rare cell types.
### Trajectory inference
[Monocle](http://cole-trapnell-lab.github.io/monocle-release/):
Tries to build a minimum spanning tree (MST) based on the reduced dimensions (independent component analysis) of gene expression data and then finds the longest path as “pseudotime”.<br>
[PAGA](https://github.com/theislab/paga):
A graph-based algorithm that estimates the connectivity between clusters by generating a graph-like map where each node represents one cluster and each edge represents a neighbourhood relation.<br>
[Slingshot](https://github.com/kstreet13/slingshot):
Besides utilizing a cluster-based MST like other tree-based methods, Slingshot then fits smooth branching curves to global lineages to obtain cell-level pseudotime.<br>
[TSCAN](https://github.com/zji90/TSCAN):
Employs a cluster-based MST approach for ordering, while the MST is built on cluster centroids instead of individual cells.<br>
[SCOEPIUS](https://github.com/rcannood/SCORPIUS):
Iteratively refines the shortest path through cluster centroids for the low-dimensionality data and then identifies the key genes using the prediction score of ordering by the random forest algorithm.<br>
[Tempora](https://github.com/BaderLab/Tempora):
A newly presented method for novel cell trajectory inference that shows great performance while prior information for time-series data is available.
### Cell type annotation
[SinlgeR](https://github.com/dviraran/SingleR):
Downloads a reference scRNA-seq dataset with cell type labels and identifies marker genes based on the fold change. Then, it calculates Spearman’s correlation coefficient between cells to be identified and cells with labels. Last, SingleR eliminates the cell type with the least correlation score and iteratively repeats the previous steps until only one cell type remains.<br>
[scMAP](https://github.com/hemberg-lab/scmap):
Utilizes the feature selection M3Drop method to find highly variable genes (HVGs) and then calculates the similarities between new cells and reference cells.<br>
[scPred](https://github.com/powellgenomicslab/scPred):
Leverages orthogonalization and dimensionality reduction of expression values to generate a support-vector machine (SVM) model for prediction.<br>
[scMatch](https://github.com/asrhou/scMatch):
Directly annotates single cells by identifying the best match in the reference datasets.<br>
[Cellassign](https://github.com/Irrationone/cellassign):
Utilizes prior cell-type marker genes to build a probabilistic model for annotation.<br>
[SCSA](https://github.com/bioinfo-ibms-pumc/SCSA):
Combines the prior knowledge of marker genes and user-defined information to annotate cell types based on an annotation model.
### Integrating dataset
