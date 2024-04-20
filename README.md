# GFPT2-scRNAseq
R codes to reproduction figures
To investigate the TIME diversity in GFPT2-knockdown tumors, we conducted single-cell RNA sequencing (scRNA-seq) on a pooled sample of 24,777 cells derived from three EGFR-mutated LLC C57BL/6N xenografts, each treated with either shNC or shGFPT2 (n=3 per group). Tumor tissues were washed in PBS, minced, enzymatically dissociated with 0.1 % trypsin for 8 minutes, followed by 0.8 mg/ml collagenase type I for 60 minutes at 37 °C with 5 % CO2, including intermittent vigorous shaking. The cell suspension was filtered through a 70-μm strainer, red blood cells were lysed, and the remaining cells were suspended in PBS for single-cell 3’-cDNA library construction using the 10X Genomics Chromium Single Cell 3’ protocol. The encapsulation, cDNA synthesis, and subsequent RNA-sequencing were conducted by Gene Denovo, Guangzhou, China.
Single-cell RNA-seq libraries were sequenced on Illumina NovaSeq using 150 nt paired-end reads. Data processing was performed with Cell Ranger 4.0.0, adhering to default and recommended parameters. Reads were aligned to the Mus musculus reference genome (Ensembl_release109) using STAR. After initial processing with the Seurat package into Seurat Objects, mitochondrial gene representation was assessed for quality control. Cells were excluded based on the following criteria: mitochondrial gene content over 10%, presence of more than 7,000 genes (nFeature > 7000), or a total count above 100,000 (nCount > 100,000). Post-filtering, the dataset was normalized and subjected to Principal Component Analysis for dimensionality reduction. Integration of different samples was performed with Harmony (Broad Institute), and clustering was conducted using the t- SNE algorithm. Cluster-defining marker genes were identified, with the top 10 markers delineating each cluster. CellChat was used for cell-cell communication analysis.
