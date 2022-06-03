# Assignment-3
SLE712 Assignment 3

Question 1: To begin, the link to be used was assigned as "URL" using"<-" before "download.file" was used to download the file the link was for. The download was named "gene expression" through "destfile=" function. read.table(URL,stringsAsFactors=FALSE, header=TRUE) was utilized to place the data in a data frame format and properly place the rows and columns. This data frame was assigned as data. "head" and "str" functions were used to view the data of the data frame before "rownames" was used to ensure that the gene identifiers were set as the row names. Finally the functions "data[1:6,]" and "rownames(data[1:6,]) was used to identify the first six genes.

Question 2: In the first step required to calculate all mean values of the columns we used the ncol function to find the number of columns present. After this we used the rowMeans function to calculate the mean of all of the columns. After this we assigned a seperate column called Mean with which the column means. After this I entered the code data [1:6,] to get the answer for just the first six rows.



Question 4: For this question in order to find the number of genes with a mean that was greater than 10 we used the data$Mean>10 to find out which of the data which had means greater than 10 in terms of true/false statements.  After this we utilized the which function which gave us which data points had the mean greater than 10. We then attributed this to the variable dt<-data[which(data$Mean<10),] and then used the code nrow(dt) to find the number of genes with a mean of greater than 10. The number of genes with a mean value higher than 10 was 35988.

Question 6: The link to be used was assigned as "url" using "<-" before "download.file" and "destfile" functions were used to download and name the file as "growth_data". As the file was a csv file the fuction "read.table(url,sep = ",",header=TRUE,)" was used to convert the data into a data frame before being assigned as "inf". "headinf" was used to view the data frame. Finally, "colnames(inf)" was used to obtain the names.

Question 7: To find the mean and standard deviation, we used the "mean" and the "sd" functions followed by the name of that particular site in a particicular year. To make it look clean and short we assigned variables to the means and standard deviations. The mean and standard deviation  for the mean circumference in 2005 was 5.077 and 1.054462 respectively. The mean and standard deviation for the circumference in 2020 was 49.912 and 22.17979 respectively

Question 8: Function grep("northeast",inf$Site) to obtained the positions of northeast sites. identify positions  The function was assigned as "ne". Similar procedure was done for the southwest site where grep("southwest",inf$Site) was used to obtain the positions of southwest sites and assigned as "sw". Function "ne2020<-inf[ne,6]" and ne2005<-inf[ne,6] was used to identify the southwest sites at the start and end of the study. This was similarly achieved with the northeast sites of the study using "ne2005<-inf[ne,3]" and "ne2020<-inf[ne,3]". "boxplot(ne2005,ne2020,sw2005,sw2020, ylab="Tree circumference",main="Growth measurements", at=c(1,2,3,4),
        names =c("northeast 2005","northeast 2020","southwest 2005","southwest 2020"))" function was used to produce the boxplot containing data from all the sites from 2005 to 2020.
        
        
        
        
 Question 10: In order to find the p values firstly, we found the difference in the mean growths at both sites between 2020 and 2010. After this we used the functions t.test and wilcox.test for the differences at the two sites. After this, we found the pvalue by using the functions 
"pval <- rest.test$p.value" where rest.test was the result of the t test and we were subsetting to find the p value. The same thing was done for the wilcox test but the varibles used in that case was rest.test2 and pval2. The value of p for the t test was 0.06229256. The p value for the wilcox test was 0.1565666.




Question 2 (Part 2): To answer this question  we used the as.numeric and the sum functions to find the length of the of all the coding sequences. For anaerococcus the length was 3978528 and for E coli it was 2011938. To make the boxplot I used the boxplot function to compare the mean sequence length for both of these organisms. The box plot shows that the mean and median value for sequence length was higher for anaerococcus compared to E.coli. The box plot also showed a higher interquartile range for Anaerococccus compared to E.coli.
