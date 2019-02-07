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
