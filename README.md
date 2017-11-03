# Scan_phasiRNA
Scan_phasiRNA: a program to find loci with 21nt phased siRNAs (such as ta-siRNA gene TAS) using the Howell algorithm

This program should be used by perl.
Before you use the program, you should put the needed files in the same folder with this program.
Following I will intrduce the way to use.
1. Edit the program Scan_phasiRNA.pm
You can edit the program use the UltraEdit or some editors like this. 
In the line 5, 
checkPhaseSignals("your_name", "your_name.fa", "your_name.map", "your_reference.fa", "your_name_phase.info", "your_name_most_abundance_sRNA.fa");

"your_name should be replaced with your smRNA file name.
your_name.fa is your smRNAs fasta file.
your_name.map is your smRNAs that maps to the reference geneome.
your_name_phase.info is the result that would output.
your_name_most_abundance_sRNA.fa is the result that would output."

For example,
checkPhaseSignals("GmaxsRNA", "GmaxsRNA.fa", "GmaxsRNA.map", "Gmax_189.fa", "Gmax_phase.info", "Gmax_most_abundance_sRNA.fa");
######
so after you replace the words, please save it and quit.

2. Usage
perl Scan_phasiRNA.pm

3. Requirement
a. the title of your smRNA.fa
>t000001 reads_numer
ATTTCGGAAGCCCGTTTTTTG

e.g. 
>t000001	10
ATTTCGGAAGCCCGTTTTTT

the 10 means there are 10 tags.

b. the format of your mapping file 

e.g. 

t000001	chr1	5000	5020	+
t000012	chr1	6000	6021	-

4. explanation of the result files
your_name_phase.info would be like this.

chrA01	53981	54190	21	3	54065	1.94591014905531	21
chrA01	54384	54635	29	3	54468	1.79175946922805	21
chrA01	95124	95396	34	4	95271	6.18208490671663	21
chrA01	95568	95819	36	3	95652	2.30258509299405	21
chrA01	320614	320802	7	3	320698	1.6094379124341	21
chrA01	400019	400291	38	4	400166	8.0507033814703	21
chrA01	782022	782315	26	4	782127	5.12989871492307	21
...
the meaning of each column
chrosome, phase loci start, phase loci end, reads numer of sRNAs, unique sequences of sRNAs, the peak phase signal location, the phase score, the phase length
###########
your_name_most_abundance_sRNA.fa would be like this.

>t0529034
TGGAACCAGCTTTTGAATTTA
>t0397041
AAATTGGTGCGTTTGCGGGAT
>t0127560
ATCCTCCCGCAACCGCCCGCA
...
#######################################
