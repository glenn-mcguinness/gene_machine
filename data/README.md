# DATA Directory

We are using data from the following two papers for our project:

- [Li et al. 2016](http://www.plantphysiol.org/content/172/2/1334.long)
- [Ohashi-Ito et al. 2010](http://www.plantcell.org/content/22/10/3461.long#sec-14)

Both papers store their data in Gene Expression Omnibus (GEO) using GEO accession numbers [GSE20586](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE20586) and [GSE77153](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE77153).

Both datasets have gene expression data at 0 and 12hrs from the same Affimetrix microarray (ATH1 genome array for *Arabidopsis*). Each paper has normalized the expression data in different ways:

- Li et al. 2016 took the raw CEL files from the microarray chip reader and evaluated them using the Robin software package. Expression levels for each probe set were estimated by GC-robust multi-array (GCRMA) analysis uring R package `gcrma`. Their expression values are log2 GCRMA values, which is a normalized value.

- Ohashi-Ito et al. 2010 were less descriptive in their methods and data files about how the data were acquired. The chip data was read using Affimetrix GeneChip Operating Software (V1.4). There is little information about what the given expression values represent, other than that they are normalized. Perhaps looking into this software will make it more clear.

## Project Design

#### Li et al. 2016

This paper targets VND7, which can be forcefully overexpressed with the addition of DEX. They have expression data from samples taken at time 0, at time 12 hrs with the addition of DEX, and time 12 hrs without the addition of DEX.

#### Ohashi-Ito et al. 2010

This paper targets both VND6 and SND1 by using cell cultures that were created with tagged VND6 or tagged SND1 that will become overexpressed with the addition of estrogen. They have expression data from samples taken at time 0 for each of wild type, VND6-tagged, and SND1-tagged cells, and well as time 12 hrs after the addition of estrogen for wild type, VND6-tagged, and SND1-tagged cells.

## Data Format

This folder contains an R Markdown file (see Files) that extracts the data from GEO using the accession numbers, cleans & filters it, and exports two csv files, one for each paper's data. The final csv's have the following format:

- **li_data.csv** : 342,150 observations of 5 variables (long format)
- **ito_data.csv** : 410,580 observations of 5 variables (long format)

The variables are the same for both files: "gene_id", "sample", "expression", "treatment", "age".

## Files

The following files are found in this directory:

- [data_download_and_manipulation.Rmd](https://github.com/glenn-mcguinness/stat540FinalProject/blob/master/data/data_download_and_manipulation.Rmd) : Run this Rmd file to download the data, clean it, filter it, and produce two csv files, one for each paper. The csv files contain only the data that is relevant for our project, and the data is in tidy (long) format that is ready for analysis.
