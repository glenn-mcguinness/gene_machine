Initial Proposal
================
**Team Brocoli**
January 23 2019

Title of project
----------------

This is initial proposal for **Team Brocoli**.

Our team members are:

<table style="width:32%;">
<colgroup>
<col width="13%" />
<col width="18%" />
</colgroup>
<thead>
<tr class="header">
<th>Github ID</th>
<th>Name</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span class="citation">[@garyzhubc]</span>(<a href="https://github.com/garyzhubc" class="uri">https://github.com/garyzhubc</a>)</td>
<td>Gary / Peiyuan Zhu (MSc, Statistics)</td>
</tr>
<tr class="even">
<td><span class="citation">[@glenn-mcguinness]</span>(<a href="https://github.com/glenn-mcguinness" class="uri">https://github.com/glenn-mcguinness</a>)</td>
<td>Glenn McGuinness (MSc, Statistics)</td>
</tr>
<tr class="odd">
<td><span class="citation">[@janxue]</span>(<a href="https://github.com/janxue" class="uri">https://github.com/janxue</a>)</td>
<td>Jan Xue (MSc, Botany)</td>
</tr>
<tr class="even">
<td><span class="citation">[@j-schaub]</span>(<a href="https://github.com/j-schaub" class="uri">https://github.com/j-schaub</a>)</td>
<td>Jessica Schaub (MSc, Oceanography)</td>
</tr>
<tr class="odd">
<td><span class="citation">[@ymkng]</span>(<a href="https://github.com/ymkng" class="uri">https://github.com/ymkng</a>)</td>
<td>Michelle Kang (MSc, Bioinformatics)</td>
</tr>
</tbody>
</table>

Our project is based on the 2018 paper [Transcriptome and DNA methylome reveal insights into yield heterosis in the curds of broccoli (Brassica oleracea L var. italic)](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-018-1384-4?fbclid=IwAR3glcIlScIMQzxMjWtuaDowqrv7DlZbzAjrTAiHRlXkRfWdyfWgt_BqCW4).

*Refference*

BMC Plant Biology **18**:168 <https://doi.org/10.1186/s12870-018-1384-4>

Proposal
--------

The following proposal is meant to give an outline of our project with an introduction, objectives, description of the data, proposed major analysis, and a breakdown of assigned tasks.

### Abstract

Hybrid vigour or heterosis is the improved quality or trait in the offspring as a result of mixing the genetic contributions of its parents. As an illustration, brocoli have flowers that pack densely to form the head which is the main edible part of the plant. When breeding disimillar strains of brocoli their offspring can form much larger heads of brocoli as demonstrated by figure 1.

![Brocoli heterosis](https://scontent.fyka1-1.fna.fbcdn.net/v/t1.0-9/49213408_10218077757916241_2440798217458155520_n.jpg?_nc_cat=111&_nc_ht=scontent.fyka1-1.fna&oh=d67a2a1ec54157595a7320d8cbed3bc3&oe=5CFB074F).

Figure 1. Hybrid vigour demonstrated by the larger head size of the hybrid offspring in comparison to the parents.

In order to explore the genetic and methylomic basis of this phenomenon as well as the contribution from each parent we will be analyzing RNA-seq and Whole Genome Bisulfite Sequencing (WGBS) data from [Li et al. 2018](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-018-1384-4) from parent and offspring brocoli that exhbited hybrid vigour.

The data transcriptomic and methylomic data associated with this paper can be found [here](https://static-content.springer.com/esm/art%3A10.1186%2Fs12870-018-1384-4/MediaObjects/12870_2018_1384_MOESM2_ESM.zip).

<We will first explore the data through graphical visulaization, for example heat maps of RNA seq data. After that to compare the different gene expressions and epigenetic characteristics we will use ANOVA or analysis of variance for parental and hybrid offspring data.> --&gt; Gary and Glenn??? maybe add more

### Motivation

[Li et al. 2018](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-018-1384-4) demonstrate that:

-   a
-   b
-   methylation site differences were greater between parent-parent than parent-hybrid.

### Goals

based on the data collected from Li et al. 2018, we will :

1.  Reconfirm their results by trying to reproduce their (1) clustering analysis of the RNA- seq data between the groups of parents and offpring that the authors have already defined, (2) their differential expression analysis to see if we obtain the same differentially expressed genes that they did wioth visualization through a heat map and dendrogram

2.  Do the differentially expressed genes in the hybrid offspring also correlate with close by methylation differences. To visualize this we will compare the differences in methylation amongst differentially expressed genes in a scatter plot. Moreover, Li et al 2018 distiguish the methylation sites into 2 different data sets, methylated and hypomethylated.

3.  Do we consider the expression or methylation data different between the sets of parents. WHat about the offspring. In order to address this we can inlcude parents and offspring as a factor and test if they are distinct groups through **statical means**.

*We can find genes that were differentially expressed between parents and offspring.Instead of treating them sepparately, we will try pooling the parents and pooling the offspring data. &lt; unsure about this&gt;*

### Description of Data

the data provided from Li et al. 2018 paper :

-   RNA seq data with x. the samples included are :

-   Raw methylation dat with number of counts
-   sample description here

### Methods and Division of Labour

-   Test whether the parental lines more simmilar to each other than to the offspring with regards to the expression data? how about the methylation data? (cluster analysis)
-   Find differentially expressed genes with two approaches. First try between each parent child triad. Then try again by pooling the parental data and pooling the child data. How different are these results?
-
