# DATA Directory

We are using data from the following two papers for our project:

- [Li et al. 2016](http://www.plantphysiol.org/content/172/2/1334.long)
- [Ohashi-Ito et al. 2010](http://www.plantcell.org/content/22/10/3461.long#sec-14)

Both papers store their data in Gene Expression Omnibus (GEO) using GEO accession numbers [GSE20586](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE20586) and [GSE77153](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE77153).

The following files are found in this directory:

- [data_download_and_manipulation.Rmd](https://github.com/glenn-mcguinness/stat540FinalProject/blob/master/Data/data_download_and_manipulation.Rmd) : Run this Rmd file to download the data, clean it, filter it, and produce two csv files, one for each paper, with only the data that is relevant to our project.