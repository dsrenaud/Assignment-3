# Assignment-3
SLE712 Assignment 3

Question 1: To begin, the link to be used was assigned as "URL" before download.file was used to download the file the link was for. The download was named "gene expression" through "destfile=" function. read.table(URL,stringsAsFactors=FALSE, header=TRUE) was utilized to place the data in a data frame format and properly place the rows and columns. This data frame was assigned as data. "head" and "str" functions were used to view the data of the data frame before "rownames" was used to ensure that the gene identifiers were set as the row names. Finally the functions "data[1:6,]" and "rownames(data[1:6,]) was used to identify the first six genes.
