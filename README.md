# Project Bioinformatic Resources
This repository contains the project done for the course of Bioinformatic Resources (held by Prof. Romanel, a.y. 2022-2023) @ University of Trento. 

Project developed by:
- Annalisa Xamin [@annalisaxamin](https://github.com/annalisaxamin)
- Nicola Perotti [@nicolaperotti](https://github.com/nicolaperotti)

## Project description
The project consists in the analysis of RNA-seq count data of Lung Adenocarcinoma extracted from the Cancer Genome Atlas (TCGA). From the original TCGA data 50 cases (tumor samples) and 50 controls (normal samples) were randomly selected.

The analysis consists of the following steps:
1. Load the data
2. Extract only protein coding genes
3. Perform differential expression analysis (`edgeR`). Select up- and down-regulated genes using a p-value cutoff of 0.01, a log fold change ratio >1.5 for up-regulated genes and < (-1.5) for down-regulated genes and a log CPM >1.
4. Perform gene set enrichment analysis (`clusterProfiler`)
5. Visualize one pathway you find enriched using the upregulated gene list (`pathview`)
6. Identify which transcription factors (TFs) have enriched scores in the promoters of all down-regulated genes.
7. Select one among the top enriched TFs, compute the empirical distributions of scores for all PWMs that you find in MotifDB for the selected TF and determine for all of them the distribution (log2) threshold cutoff at 99.75%.
8. Identify which down-regulated genes have a region in their promoter with binding scores above the computed thresholds for any of the previously selected PWMs.
9. Find PPI interactions among differentially expressed genes (STRING)
10. Identify and plot the largest connected component (`igraph`)

## Repository structure
The repository is structured as follows:
- `RData/`: contains the data used for the analysis
- `output/`: contains the output obtained from the analysis
- `data_STRING/`: contains the data used for the network analysis
- `Project_Bioinfo.Rmd`: contains the **script** used for the analysis
- `Project_Bioinfo.pdf`: contains the **report**

## Output
The output of the analysis is available in the `output/` folder. It consists of:
- `DEGs.txt`: contains the list of differentially expressed genes.
- `down_DEGs.txt`: contains the list of down-regulated genes.
- `up_DEGs.txt`: contains the list of up-regulated genes.
- `ego_BP_down.pdf`: contains the plot of the enriched GO terms related to the Biological Process for the down-regulated genes.
- `ego_BP_up.pdf`: contains the plot of the enriched GO terms related to the Biological Process for the up-regulated genes.
- `ego_MF_down.pdf`: contains the plot of the enriched GO terms related to the Molecular Function for the down-regulated genes.
- `ego_MF_up.pdf`: contains the plot of the enriched GO terms related to the Molecular Function for the up-regulated genes.
- `eWP_down.pdf`: contains the plot of the enriched GO terms related to the pathways for the down-regulated genes.
- `eWP_up.pdf`: contains the plot of the enriched GO terms related to the pathways for the up-regulated genes.
- `enriched_genes_id.txt`: contains the list of enriched genes (output of task 8)
- `ens_gene_id_down.txt`: contains the gene IDs of the down-regulated genes used to retrieve the network from STRING.
- `hsa05144.pathview.png`: contains the plot of the most enriched pathway for the up-regulated genes.
- `hsa05144.png` and `hsa05144.xml` contains info about the most enriched pathway.