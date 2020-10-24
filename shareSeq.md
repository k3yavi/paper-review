# Paper: Chromatin Potential Identified by Shared Single-Cell Profiling of RNA and Chromatin

## How to validate Specificity and data quality of a technology:
	* Human and mouse reads were well separated on chromatin and transcriptome profiles.
	* Remove Doublet and check low collision rate on the above barnyard experiment.
	* On average ~2.5k RNA UMI/cell and ~8k fragments/cell is considered good stats according to the authors.
	* concordance with previous scATAC-seq / RNA-seq studies through library-size on wide range of tissue.
	* RNA reads (starting with cells or nuclei) are enriched for intronic regions, similar to single-nucleus RNA sequencing (snRNA-seq).
	* chromatin accessibility at the NFkB1 locus and NFkB1 gene expression significantly co-varied across single cells on RNA. (Fig-1F).
	* similar data quality (through the fraction of reads from genomic regions) when starting with cells or nuclei (Figures S2E–S2G).
	
## How to show Congruence between Modalities:
	* Disjoint clustering on each modality and compare the UMAP so that each mode separates the clusters defined on another.
	* Heatmap showing the proportion of cells in one modality that overlaps with clusters from another (Fig 2F).
	* Based on previous literature connect some small subfeatures between two modalities, for example Dlx3/Sox9 (zeb1/sox5) are transcriptional activator(repressor) which increases(decrease) gene expression.
	* Give examples of populations which are distinguishable in one and not in another modality.
	
## How to Validate a tool which connects multiple modalities:
	* Connect the modalities and compare it with ground truth we know because of shared CB.
	* Search for orhtogonal methods ex: CRISR-based perturbation studies / HiChip which gives you ground truth on some subfeatures which are connected.
	* Look for Negative Control examples for features which should not be connected.
	* Look for difficult features for example well known gene clusters (Histone, Hox, and Keratin) where the tool fails.
	* Explain results on some well known universally accepted housekeeping features.
	* If possible provide an unsupervised approach to identify key feature combination without the need to know the functional properties such as cell-types.
	
## How did they sell the computational IP of the paper DORC:
	* DORC identifies on the full population highly overlaps on the sub-population.
	* Show strongly enriched for known key regulators with DORC across lineages.
	* Significant differences in DORCs even between closely related sub-populations.
	* Show cell-type specific DORC and DORC predicts mutual exclusion.

## How to design lineage related study and the analysis:
	* First know the broad group of cell-types (progenitor and differentiation) and their differentiation timeline across the pseudotime.
	* Divide the landscape into multiple lineages to study indepandantly.
		* This paper had three (TAC -> IRS, medulla, and cuticle/cortex)
	* If one has multiple modailties pick one linege and check if a well known DE features lags in activation through lineage progression across modalities.
		* Authors compute the modalities by computing ‘‘residuals’’ (defined as the difference of chromatin accessibility and expression of the gene
	* Can we figure out One feature combination acorss modality affects another through a lineage:
		* Very interesting hypothesis: **TFs that prime are distinct from TFs that activate enhancers**. 
	* Using the learnt connection between two modalities can we predict the future of the cell?
		* Author use the nearest cell across modalities to connect and define future calling chromatin potential.
	
## Potential Problems/Challenges in the study:
	* Statistical significance of peak-gene features are based on thier ranking on number of significant associations, which can be potentially problematic as it's dependant on a threshold value.
	* Hand wavy: Only 34.4% of DORCs active in hair follicle stem cells (HFSCs) overlap with super-enhancers identified in these same cell types, suggesting that DORCs may encompass other mechanisms promoting formation of enhancer clusters.
	* Figure 4E is great as it shows the enghancer -> promoter -> intron -> exon sequenctial activation however there is only one example in the paper, is ther a way to extract multiple such features ?