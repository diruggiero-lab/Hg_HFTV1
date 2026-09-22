## CODE AND SCRIPTS 

- **HFTV1_REANNOTATION.Rmd** - Documentation for reannotating the HFTV1 genome. Includes consolidation of revisions based on Pharokka/Phold, Ribo-Seq data +/-HHT, and various annotation file exports for downstream analyses.

- **HFTV1_gp17_EXPRESSION.Rmd** - Documentation for analysis of the expression of individual regions (5' and 3') of the HFTV1 gene gp17. Includes region-specific calculation of cumulative expression (in RNA-seq or Ribo-seq) and of translation efficiency.

- **HG_INF_RNA_RBO_DE_TE.Rmd** - Documentation for differential expression analysis and translation efficiency analysis of RNA-seq and Ribo-seq data.

## ANNOTATIONS AND REFERENCE FILES

- **HFTV1_NCBI_PP_consensus.gff** - HFTV1 annotation containing features derived from NCBI annotations and Pharokka/Phold (PP), as well as revised descriptions for structural genes based on Zhang et al. (2025) cryo-EM of HFTV1 virions.

- **HFTV1_Hg.gff** and **HFTV1_Hg_gff.csv** - Merged HFTV1-*Hg* annotations, with revisions of HFTV1 ORFs based on translation start site mapping using Ribo-seq +/- harringtonine. HFTV1 annotation with Pharokka/Phold features (see above) was used as input in the construction of this file. CSV format included for convenient browsing outside of formal analysis.

- **cog_code_viral_mods.csv** - COG code used for functional analysis of differentially expressed genes. Based on COGs and arCOGs. Since standard categories could not be assigned to most HFTV1 genes, custom categories were added with unique identifiers. Correlation between these custom categories and viral genes can be found in output of DE analyses (e.g., see **RBO_master.csv**).

## RESULTS FILES

Note: other results files are available in the supplemental tables of the publication that accompanies this work.

- **RBO_master.csv** - Master spreadsheet of genes with differential ribosome occupancy based on Ribo-seq (0, 5, 15, 30, 60, and 180 min post-infection). Fields include cluster family assignment, cluster assignment, functional annotations, and various expression values.
  - RBO_DE - Redundant column denoting whether genes were differentially expressed (DEG) or not differentially expressed (NDEG).
  - clu_fam - Cluster family assigned from secondary clustering step. Values: A, B, C, D, E, or F. 
  - clu - Cluster assigned from first clustering step. Values: 1-27 (all genetic elements except native Hg plasmid pHGLR3) or 41-42 (Hg plasmid pHGLR3).
  - entity - Hg or HFTV1
  - seqnames - Genetic element identifier
  - gene_id 
  - protein_id
  - source - Origin of feature annotation
  - strand
  - eggNOG_gene_name - Derived from arCOG annotation via eggNOG. 
  - product
  - Description - Derived from arCOG annotation via eggNOG.
  - COG_desc_lvl1 - Broadest level of COG annotation categories. Values: cellular_processes_and_signaling, information_storage_and_processing, metabolism, poorly_characterized, or no_hits.
  - COG_desc_lvl2 - Detailed level of COG annotation categories. Derived from arCOG annotation via eggNOG and additional custom categories for HFTV1.
  - COG_category - Single-letter code for COG annotation categories. Derived from arCOG annotation via eggNOG and additional custom categories for HFTV1.
  - COG_ora_fdr_p_val - Significance value for over- or under-representation of a given COG category per cluster family. Corrected for FDR by BH adjustment. This value corresponds to the COG category assigned to each gene and is not unique to every gene.
  - baseMean - Mean read counts per gene. See DESeq2 documentation.
  - padj_bh - Significance value for differential expression of a given gene. FDR-corrected by BH adjustment based on total number of tests conducted, accounting for genes on all genetic elements including pHGLR3.
  - sfn_000 to sfn_180 - sizeFactor-normalized data of each gene at each time point. See DESeq2 documentation.
  - rld_000 to rld_180 - Rlog-transformed, sizeFactor-normalized data at each time point. See DESeq2 documentation.
  - L2FC_005_v_000 to L2FC_180_v_000 - L2FC data at each time point relative to 0 min post-infection.
  - TE_000 to TE_180 - Translation efficiency of each gene at each time point. 
