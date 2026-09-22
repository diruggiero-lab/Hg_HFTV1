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

- **RBO_master.csv** - Master spreadsheet of genes with differential ribosome occupancy based on Ribo-seq. Fields include cluster family assignment, cluster assignment, functional annotations, and various expression values. 
