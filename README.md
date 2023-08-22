# Hu_scRNA_COVID Project
![GitHub last commit](https://img.shields.io/github/last-commit/alemenze/Hu_scRNA_COVID)
[![run with docker](https://img.shields.io/badge/run%20with-docker-0db7ed?labelColor=000000&logo=docker)](https://www.docker.com/)
[![run with singularity](https://img.shields.io/badge/run%20with-singularity-1d355c.svg?labelColor=000000)](https://sylabs.io/docs/)
[![run with RStudio](https://img.shields.io/badge/RStudio-75AADB?style=for-the-badge&logo=RStudio&logoColor=white)](https://posit.co/products/open-source/rstudio/)

## Description
This is the code repository for the project through William Hu's Lab for scRNA sequencing of COVID patients subtypes vs normal healthy controls. This is the base code, and should cover what was performed for the final pass of data prior to PI delivery. Additional analysis by the PI's team may have been performed, and all communications regarding the final publication should be addressed to the corresponding author. 

## Execution
To execute this data, you can use a docker container with the preloaded libraries. Due to the relativistic nature of UMAP, your plots may generate slightly different so double check the reclustering matches the appropriate populations. The final conclusions should be identical (or nearly). 

```bash
docker run --rm -p 8787:8787 -e PASSWORD=${password} -v ~./analysis:/home/rstudio alemenze/abrfseurat:v1
```
This will run an Rstudio instance on your local machine using our prebuilt docker container version that was used for processing this data. You must define a password for the rstudio environment, and change the local directory to the appropriate path of your input data. From there, you can navigate in your browser to [localhost:8787](http://localhost:8787), and access the rstudio environment. 

Then you can follow along with the rmarkdown file provided. For ease, we used a metadata sheet to wrap our files- these are based on their original names and may be different downloading from GEO. 

## Input Data
Input data was raw .h5 matrices generated from cellranger v6. Raw fastq files and raw .h5 matrices can be found at the Gene Expression Omnibus at accession [GSE241385](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE241385)
