# Analysis of False Discovery Rate Strategies in Shotgun Proteomics

This repository contains the R code and results for a project investigating the impact of different database search strategies on False Discovery Rate (FDR) estimation in shotgun proteomics. The analysis compares an emulated concatenated search strategy against a separate, un-concatenated target-decoy search.

The primary finding is that the concatenated approach, which incorporates a competition model, identifies approximately 1.25 times more confident peptide-spectrum matches (PSMs) at a 1% FDR threshold than the more conservative un-concatenated method.

[View the Final Report](report/APE.pdf)

## Prerequisites

### Software
*   **SearchGUI:** (Version 4.3.17 or similar) for running the Comet search engine. [Download here](https://compomics.github.io/projects/searchgui.html).
*   **R:** (Version 4.0 or later) for data analysis. [Download here](https://www.r-project.org/).
*   **RStudio:** (Recommended) An integrated development environment for R. [Download here](https://www.rstudio.com/).

### R Packages
Run the following commands in your R console to install the necessary packages.

```R
# For reading FASTA files
install.packages("microseq")

# For data manipulation and plotting
install.packages("dplyr")
install.packages("ggplot2")
install.packages("stringr")

# For reading mass spectrometry data files (from Bioconductor)
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install(c("mzR", "Spectra", "MsBackendMzR", "Biostrings"))


