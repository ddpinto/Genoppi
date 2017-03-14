# Genoppi v2.0
Genoppi is an interactive web application for analyzing and visualizing integrated experimental human proteomics data with genetics. It provides a visual interface for generating a variety of interactive plots to quality control raw data, integrate with GWAS dataset, identify known protein interacting partners, determine protein families present and offer easy visualization.

## Installation
Genoppi requires R and RStudio. For best results, use the latest version of R.<br>
R is available at https://www.r-project.org/<br>
RStudio is available at https://www.rstudio.com/products/rstudio/download/<br>


Genoppi depends on several R packages. Run the following command from within RStudio to install them.
```r
source("https://bioconductor.org/biocLite.R")
biocLite("limma")
install.packages(c("shiny", "shinyjs", "plotly", "stringr", "VennDiagram", "rmarkdown", "plyr", "data.table", "ggplot2", "RColorBrewer"))
```

## Running Genoppi locally
To modify the code to suit one's needs, the direct download link for Genoppi is https://github.com/lagelab/Genoppi/archive/master.zip

To start local version of Genoppi, begin RStudio and run the following commands.
```r
library(shiny)
runApp("/path/to/your/local/Genoppi/folder")
```

## Preparing your data
<h3>Human experimental proteomics data</h3>
Genoppi takes experimental IP-MS/MS results of bait pull down or full proteome data as text file. This file should include corresponding gene names or Uniprot accession numbers and either <br>
(1) results of statistical analyses or <br>
(2) values of logarithmic fold change (logFC, the ratio of case to control) for two replicates in chosen condition.

The headers must include<br>
(1) <b>gene, logFC, FDR, pvalue</b> or<br>
(2) <b>gene, rep1, rep2</b><br> or<br>
(1) <b>accession_number, logFC, FDR, pvalue</b> or<br>
(2) <b>accession_number, rep1, rep2</b><br>

Any missing values in input files may lead to improper visualization of the data and thus will be removed.


<h3>Example files</h3>
Example dataset can be found in Genoppi/example.


## Documentation and Support
Documentation may be accessed from within Genoppi interface using the "Documentation" tab.

Please address comments and questions to April Kim at aprilkim@broadinstitute.org, Edyta Malolepsza at edytam@broadinstitute.org or Kasper Lage at lage.kasper@mgh.harvard.edu.
