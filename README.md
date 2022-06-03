# Assignment-3
SLE712 Assignment 3

Question 1: To begin, the link to be used was assigned as "URL" using"<-" before "download.file" was used to download the file the link was for. The download was named "gene expression" through "destfile=" function. read.table(URL,stringsAsFactors=FALSE, header=TRUE) was utilized to place the data in a data frame format and properly place the rows and columns. This data frame was assigned as data. "head" and "str" functions were used to view the data of the data frame before "rownames" was used to ensure that the gene identifiers were set as the row names. Finally the functions "data[1:6,]" and "rownames(data[1:6,]) was used to identify the first six genes.

Question 6: The link to be used was assigned as "url" using "<-" before "download.file" and "destfile" functions were used to download and name the file as "growth_data". As the file was a csv file the fuction "read.table(url,sep = ",",header=TRUE,)" was used to convert the data into a data frame before being assigned as "inf". "headinf" was used to view the data frame. Finally, "colnames(inf)" was used to obtain the names.

Question 8: Function grep("northeast",inf$Site) to obtained the positions of northeast sites. identify positions  The function was assigned as "ne". Similar procedure was done for the southwest site where grep("southwest",inf$Site) was used to obtain the positions of southwest sites and assigned as "sw". Function "ne2020<-inf[ne,6]" and ne2005<-inf[ne,6] was used to identify the southwest sites at the start and end of the study. This was similarly achieved with the northeast sites of the study using "ne2005<-inf[ne,3]" and "ne2020<-inf[ne,3]". "boxplot(ne2005,ne2020,sw2005,sw2020, ylab="Tree circumference",main="Growth measurements", at=c(1,2,3,4),
        names =c("northeast 2005","northeast 2020","southwest 2005","southwest 2020"))" function was used to produce the boxplot containing data from all the sites from 2005 to 2020.

Part 2.

Question 4: The function "uco" is utilised for codon counting. "ecodon<-uco(cds[[2]],index="rscu",as.data.frame=TRUE)" was used to view data as a data frame while assigning it as "ecodon".  
Function: "%>%
  kbl() %>%
  kable_paper("hover",full_width=F)" was used produce tables using kableExtra. These tables allowed viewing of various codons as well as their frequencies. kableExtra function was also used to find the biases for most used and least used codons for E coli and anarococcus 
  e.g.:"ecodon%>%
  kbl() %>%
  kable_paper("hover",full_width=F)". To do this high bias for E coli was assigned as "highb" and the lower biased codons assigned as "lowbias". This procedure was also follwed using annaerococcus with high bias represented by higha and lower bias codon usage as "alowbias".
