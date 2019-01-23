Data Description
================
Jessica Schaub & Michelle Kang
January 23, 2019

Below are descriptions of the data sets that are relevant for our project goals. The data can be found at [Li et al. 2018](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-018-1384-4?fbclid=IwAR3glcIlScIMQzxMjWtuaDowqrv7DlZbzAjrTAiHRlXkRfWdyfWgt_BqCW4) by downloading 'Additional file 2'.

'Additional file 2' contains 11 data sets, but only a subset of the them are relevant.

Gene Expression Data
--------------------

This data is required for Goals 1, 2, & 3, outlined in the proposal.

### *Data Set 1*

-   Data is organized into tabs along the bottom for comparisons between both parents (NKR-04 and NKR-05) and between each parent and the child (NKR-06)
-   Each sheet has the Gene ID and Transcript ID, then the expression level of the given gene/transcript for each individual (NKR-04, NKR-05, NKR-06)
-   Expression level is a normalized value, so the expression level is FPKM (fragments per kilobase of transcript per million mapped reads)
-   Columns A-D are their measured values that we can extract for our analysis, after D is calculated by the authors and something we can try to replicate to meet our goals

### *Data Set 2*

-   Same as Data Set 1, but for the Bro triad
-   Parents: Bro-10 & Bro-11
-   Child: Bro-12

### *Data Set 5*

-   Functional annotation of the genes, describes the function of the gene
-   NKR triad

### *Data Set 6*

-   Functional annotation of the gene, describes the function of the gene
-   Bro triad

Methylation Data
----------------

This data is required for Goals 2 & 3, outlined in the proposal.

### *Data Set 7*

-   Has the CG and CHG methylation data for both parent/child triads in separate sheets
-   The methylated tag, position, and sequence data describe where the methylation happens
-   The ‘clean reads’ columns are raw data (the number of reads found that had methylation at the specific positions
-   The ‘normalized methylation’ columns are what was calculated by the authors
