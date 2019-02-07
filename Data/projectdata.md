projectdata
================
michelle kang
February 7, 2019

``` r
if (file.exists("GSE77153.Rdata")) {
    # if previously downloaded
    load("GSE77153.Rdata")
} else {
    # Get geo object that contains our data and phenotype information
    geo_obj <- getGEO("GSE77153", GSEMatrix = TRUE)
    geo_obj <- geo_obj[[1]]
    head(geo_obj)
    save(geo_obj, file = "GSE77153.Rdata")
}
```

    ## Found 1 file(s)

    ## GSE77153_series_matrix.txt.gz

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   ID_REF = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## File stored at:

    ## /var/folders/_w/lnm5mj1j0hn_7__6yv1rmkvm0000gn/T//RtmpNLCLTG/GPL198.soft

    ## Warning: 64 parsing failures.
    ##   row     col           expected    actual         file
    ## 22747 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22748 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22749 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22750 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22751 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## ..... ....... .................. ......... ............
    ## See problems(...) for more details.

``` r
# Get expression data
li_data <- exprs(geo_obj)


li_metadata <- pData(geo_obj)[, c("organism_ch1", "title", colnames(pData(geo_obj))[grep("characteristics", 
    colnames(pData(geo_obj)))])]

colnames(li_metadata) = c("organism", "sample_name", "ecotype", "vector", "tissue", "treatment", "age")
li_metadata$ecotype = as.factor(gsub("ecotype/background: ", "", li_metadata$ecotype))
li_metadata$vector = as.factor(gsub("vector: ", "",li_metadata$vector))
li_metadata$tissue = as.factor(gsub("tissue: ", "", li_metadata$tissue))
li_metadata$treatment = as.factor(gsub("treatment: ", "", li_metadata$treatment))
li_metadata$age = gsub("time after induction: ", "", li_metadata$age)
```

``` r
li_data <- data.frame(li_data)
setDT(li_data, keep.rownames = TRUE)
#rename column 1


#Convert to long form
tidy_li_data <- li_data %>% 
  gather(key="sample", value="expression")
```

``` r
if (file.exists("GSE20586.Rdata")) {
    # if previously downloaded
    load("GSE20586.Rdata")
} else {
    # Get geo object that contains our data and phenotype information
    geo_obj <- getGEO("GSE20586", GSEMatrix = TRUE)
    geo_obj <- geo_obj[[1]]
    head(geo_obj)
    save(geo_obj, file = "GSE20586.Rdata")
}
```

    ## Found 1 file(s)

    ## GSE20586_series_matrix.txt.gz

    ## Parsed with column specification:
    ## cols(
    ##   ID_REF = col_character(),
    ##   GSM517073 = col_double(),
    ##   GSM517074 = col_double(),
    ##   GSM517075 = col_double(),
    ##   GSM517076 = col_double(),
    ##   GSM517077 = col_double(),
    ##   GSM517078 = col_double(),
    ##   GSM517079 = col_double(),
    ##   GSM517080 = col_double(),
    ##   GSM517081 = col_double(),
    ##   GSM517082 = col_double(),
    ##   GSM517083 = col_double(),
    ##   GSM517084 = col_double(),
    ##   GSM517085 = col_double(),
    ##   GSM517086 = col_double(),
    ##   GSM517087 = col_double(),
    ##   GSM517088 = col_double(),
    ##   GSM517089 = col_double(),
    ##   GSM517090 = col_double()
    ## )

    ## Using locally cached version of GPL198 found here:
    ## /var/folders/_w/lnm5mj1j0hn_7__6yv1rmkvm0000gn/T//RtmpNLCLTG/GPL198.soft

    ## Warning: 64 parsing failures.
    ##   row     col           expected    actual         file
    ## 22747 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22748 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22749 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22750 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## 22751 SPOT_ID 1/0/T/F/TRUE/FALSE --Control literal data
    ## ..... ....... .................. ......... ............
    ## See problems(...) for more details.

``` r
# Get expression data
ito_data <- exprs(geo_obj)


ito_metadata <- pData(geo_obj)[, c("organism_ch1", "title", colnames(pData(geo_obj))[grep("characteristics", 
    colnames(pData(geo_obj)))])]

colnames(ito_metadata) = c("organism", "sample_name", "treatment", "age")
ito_metadata$treatment = as.factor(gsub("cultured cell type: ", "", ito_metadata$treatment))
ito_metadata$age = gsub("time point: ", "", ito_metadata$age)
head(ito_metadata)
```

    ##                       organism sample_name       treatment age
    ## GSM517073 Arabidopsis thaliana  wt_0h_rep1 wt culture cell  0h
    ## GSM517074 Arabidopsis thaliana  wt_0h_rep2 wt culture cell  0h
    ## GSM517075 Arabidopsis thaliana  wt_0h_rep3 wt culture cell  0h
    ## GSM517076 Arabidopsis thaliana wt_12h_rep1 wt culture cell 12h
    ## GSM517077 Arabidopsis thaliana wt_12h_rep2 wt culture cell 12h
    ## GSM517078 Arabidopsis thaliana wt_12h_rep3 wt culture cell 12h

``` r
ito_data <- data.frame(ito_data)
setDT(ito_data, keep.rownames = TRUE)
#rename column 1
 
 
#Convert to long form
tidy_ito_data <- ito_data %>% 
gather(key="sample", value="expression")
```
