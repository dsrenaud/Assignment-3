# Assignment-3
SLE712 Assignment 3

Question 1: To begin, the link to be used was assigned as "URL" using"<-" before "download.file" was used to download the file the link was for. The download was named "gene expression" through "destfile=" function. read.table(URL,stringsAsFactors=FALSE, header=TRUE) was utilized to place the data in a data frame format and properly place the rows and columns. This data frame was assigned as data. "head" and "str" functions were used to view the data of the data frame before "rownames" was used to ensure that the gene identifiers were set as the row names. Finally the functions "data[1:6,]" and "rownames(data[1:6,]) was used to identify the first six genes.

Question 2: In the first step required to calculate all mean values of the columns we used the ncol function to find the number of columns present. After this we used the rowMeans function to calculate the mean of all of the columns. After this we assigned a seperate column called Mean with which the column means. After this I entered the code data [1:6,] to get the answer for just the first six rows.

Question 3: Previously, we obtained the mean expression of the genes using “Mean” in three different samples. Now, we subset the “Mean” from the data frame and arranged it using function “data[order(-data$Mean),]”. Here the (-) negative sign would order the data in ascending order. As per the question, the first 10 genes with highest expression would be extracted out by first sorting and saving the data as “data[order(-data$Mean),]” and then subsetting it using [ ] in a function “revsort[1:10,]”.


Question 4: For this question in order to find the number of genes with a mean that was greater than 10 we used the data$Mean>10 to find out which of the data which had means greater than 10 in terms of true/false statements.  After this we utilized the which function which gave us which data points had the mean greater than 10. We then attributed this to the variable dt<-data[which(data$Mean<10),] and then used the code nrow(dt) to find the number of genes with a mean of greater than 10. The number of genes with a mean value higher than 10 was 35988.

Question 5: The mean values of the genes in the data set was presented in a histogram having “mean” as the x-axis and  their “ frequency” on y-axis. The data (Mean) was first converted to data matrix using “as.matrix(as.matrix(data$Mean)” and then using Histogram function in R as “ hist(dmat,xlab = "Mean values",main = "Mean of gene expressions", breaks = 100). Here the “breaks” which controls the No. of bars in histogram were set to 100 to get as many bars as possible. The default break’s setting gives only 1 bar since most of the genes had close to zero mean expression. 

Question 6: The link to be used was assigned as "url" using "<-" before "download.file" and "destfile" functions were used to download and name the file as "growth_data". As the file was a csv file the fuction "read.table(url,sep = ",",header=TRUE,)" was used to convert the data into a data frame before being assigned as "inf". "headinf" was used to view the data frame. Finally, "colnames(inf)" was used to obtain the names.

Question 7: To find the mean and standard deviation, we used the "mean" and the "sd" functions followed by the name of that particular site in a particicular year. To make it look clean and short we assigned variables to the means and standard deviations. The mean and standard deviation  for the mean circumference in 2005 was 5.077 and 1.054462 respectively. The mean and standard deviation for the circumference in 2020 was 49.912 and 22.17979 respectively

Question 8: Function grep("northeast",inf$Site) to obtained the positions of northeast sites. identify positions  The function was assigned as "ne". Similar procedure was done for the southwest site where grep("southwest",inf$Site) was used to obtain the positions of southwest sites and assigned as "sw". Function "ne2020<-inf[ne,6]" and ne2005<-inf[ne,6] was used to identify the southwest sites at the start and end of the study. This was similarly achieved with the northeast sites of the study using "ne2005<-inf[ne,3]" and "ne2020<-inf[ne,3]". "boxplot(ne2005,ne2020,sw2005,sw2020, ylab="Tree circumference",main="Growth measurements", at=c(1,2,3,4),
        names =c("northeast 2005","northeast 2020","southwest 2005","southwest 2020"))" function was used to produce the boxplot containing data from all the sites from 2005 to 2020.
        
 Question 9: For getting the mean growth between 2010 and 2020, first the data was sorted for site specfic northeast and southwest for year 2010 and 2020 using "grep function” as in "grep("northeast",inf$Site) and "grep("southwest",inf$Site)", respectively.Then mean was calculated for each site for both years using "southwest_2010 <- mean(sw2010)" and “ Northwest_2010 <- mean(ne2010)”, respectively. The difference between the mean growth rate of each site on 2 years was calculated, which provided the mean growth rate of last 10 years.     
        
        
 Question 10: In order to find the p values firstly, we found the difference in the mean growths at both sites between 2020 and 2010. After this we used the functions t.test and wilcox.test for the differences at the two sites. After this, we found the pvalue by using the functions 
"pval <- rest.test$p.value" where rest.test was the result of the t test and we were subsetting to find the p value. The same thing was done for the wilcox test but the varibles used in that case was rest.test2 and pval2. The value of p for the t test was 0.06229256. The p value for the wilcox test was 0.1565666.

Part 2
Question 1:
The DNA seq of E.coli and Anaerococcus Tetradius was obtained from Ensemble bacteria  and their sequences’s URL was loaded, downloaded, and saved in the R studio. Three libraries, such as library "seqinr" for DNA sequence analysis ,  library "kableExtra" for creating HTML tables, and  library "R.utils" for providing additional functions like zip/unzipping of files was created.  First the nucleotide sequences was analyzed by listing the unzip sequence  as in “seqinr::read.fasta("ecoli_cds.fa")” and counting the number of coding sequences using “ length(cds)”. The total DNA sequences ( in E.coli were determined by using “sum(sapply(cds[1:3], length))” . Moreover, the amount of coding sequences were measured by first counting the sequences using “count(cds[[1]],3) followed by the summation using “sum(sapply(cds[1:3], length))” function. The same functions were applied for A. tetradius as well. There were significant differences between the coding sequecnes of both organisms with A. tetradius having larger No. of coding sequences, showing higher level of gene expression coding for more proteins. It means that A. tetradius have bigger genome size and encodes for many proteins adding more physiological benefits to the bacteria. 

Question 2 : To answer this question  we used the as.numeric and the sum functions to find the length of the of all the coding sequences. For Anaerococcus the length was 3978528 and for E coli it was 2011938. To make the boxplot I used the boxplot function to compare the mean sequence length for both of these organisms. The box plot shows that the mean and median value for sequence length was higher for Anaerococcus compared to E.coli. The box plot also showed a higher interquartile range for Anaerococccus compared to E.coli.

Question 3: After loading and initial assessment of the DNA sequence of both organisms, the frequency of the DNA bases (A,T,G,C) in the perspective organism was calculated. After” unlisting” the DNA sequence and saving it as “ecodna <- unlist(cds)”, its frequency was measured using function “ count(ecodna, word size=1)” with word size=1 giving results as of single DNA base. Then, the sequences were translated using “translate([[cds]],1)” . After unlisting the translated sequences, the frequency of amino acids were determined in total sequence saving and running “anprot_composition <- count (anpro, alphabet = aa, wordsize = 1)”. The results for amino acid and DNA sequences for each organism explains that certain amino acids, such as Alanine, Glycine, and Valine are comparatively more abundant in E.coli than A. tetradius. Moreover, the Tryphtophan is the Leucine is the most prevalent in both of these organism. Overall. E.coli has amino acids with higher frequency than in T.tetradius despite of having larger DNA bases and genome.

Question 4: Using "uco" for the codon count to make the function "uco(cds[[2]],index="rscu",as.data.frame=TRUE)" (assigned as "ecodon"), data the codon usage of E coli was produced. by inputing "ecodon" into the function:

"ecodon %>%
  kbl() %>%
  kable_paper("hover",full_width=F)"
  
  kableExtra was used to produce a codon usage table for E coli. Next, the function "ecodon[order(ecodon$freq),]" was used to arrange the data in order from the smallest frequency to the largest frequency( assigned as "lowbias"), follwed by function
  
  "%>%
  kbl() %>%
  kable_paper("hover",full_width=F)" in order to produce a codon table arranged in order of ascending frequency. Note: %>% is know as the forward pipe operator in R and chains commands with the next forward pipe operatot. The same steps were taken to obtain a higher frequency bias but the function ecodon "[order(-ecodon$freq),]" (assigned as highb) was used. the "-" placed before ecodon transforms the function i such a way that the resulting table from kableExtra was arranged in descending order instead starting with the largest frequencies first then going down to the smallest.
  
  The same procedure was followed to obtain the codon usage tables for Anaetococcus but instead "uco(an[[2]],index="rscu",as.data.frame=TRUE)" was assigned as acodon. kableExtra was used to produce condon tables of Anaerococcus using functions:
  
  "acodon %>%
  kbl() %>%
  kable_paper("hover",full_width=F)". Afterwards the low frequency bias and high frequency bias codon tables were produced by the functions: "alowbias<-acodon[order(acodon$freq),]" and "higha<-acodon[order(-acodon$freq),]" through kableExtra.
In the analysis of the tables for anaerococcus what was evident was that the number of codons at the higher bias especially at frequencies of 0.01 and 0.02 were more than 20 compared to the number of codons at the lower bias with only around 11 codons present between 0.02 and 0.04 and only one codon at the 0.06 frequency. As for E.coli the numebr of codons at high bias frequuency of 0.01 had more than 20 codons. From 0.01-0.03 the number of codons is less compared to that of the anaerococcus. From 0.03-0.05 the number of codons reduce just like in anaerococcus but they have more codons present in that level of bias for anaerococcus compared to E.coli.

Question 5:  To begin, “pro” and “anpro” from previous question was used in the formula “count (pro,alphabet= aa,wordsize=``, freq=TRUE)” and “count(anpro,alphabet= aa,wordsize=``, freq=TRUE)” respectively. These functions were applied three times for wordsizes 3,4 and 5 to obtain the corresponding sequence lengths of each organism required. These lengths were assigned as “ecomp3”, “ecomp4”, and “ecomp5”, for E coli and “acomp3”, “acomp4”, “acomp5” for Anaerococcus. Lower bias and lower bias were found using function “head(sort(acomp(),increasing=TRUE),n=10L) for Anaerococcus with “n=10L” being used to focus on 10 sequences specifically. “increasing=TRUE” was utilized to place order of frequency form the most under represented to the most over represented. The reverse was achieved with function “head(sort(acomp(),decreasing=TRUE),n=10L)” where using “decreasing=TRUE place the order of frequency from highest to lowest, allowing for the top 10 over represented protein sequence kmers to be identified. To find matching E coli the “grep”  function was utilized to manually find the position of the sequences of E coli that match those of Anaerococcus.This was achieved through the function “grep((""),rownames(ecomp()))” in which the sequence and length was inputted. These higher and lower represented sequences for length 3-5 were assigned as “eoverep()” and “eunderep()” for E coli and “aoverep()” and “aunderep” for Anaerococcus respectively. Finally, by using functions:
 

	“plot(eoverep3,type="b", col="yellow", xlab="codon",ylab="protein frequency")
	lines(eoverep4,type="b", col="pink")
	lines(eoverep5,type="b", col="gray")
	lines(eunderep3,type="b", col="blue")
	lines(eunderep4,type="b", col="red")
	lines(eunderep5,type="b", col="black")”
	
	“plot(aoverep3,type="b", col="yellow", xlab="codon",ylab="protein frequency")
	lines(aoverep4,type="b", col="pink")
	lines(aoverep5,type="b", col="gray")
	lines(aunderep3,type="b", col="blue")
	lines(aunderep4,type="b", col="red")
	lines(aunderep5,type="b", col="black")”
	
A plot was created for comparison of over and underrepresented sequences of both organisms.
By observing the graphs, it can be deduced that at length 3, Anaerococcus has a significantly greater over representation of sequence LLL than E coli. This also appears to be the case for lengths 4 and 5 where Anaerococcus also displays a higher representation. Anaroccoccus also appears to have the least expressed sequences with the frequencies lying at 0 for all lengths whereas in E coli, the lengths are appeared slightly above 0.

