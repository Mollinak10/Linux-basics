make a folder and work in that. 


mamba install bioconda::fastqc -y
to check 
fastqc --version 
FastQC v0.12.1

mamba install sra-tools
prefetch SRR35012817
fastq-dump SRR35012817  (if file not paired) 


fastq-dump --split-files SRR35012817 (if file paired) 


mkdir outqc 
mv *.fastq 



fastqc -o outqc/ SRR35012817_1.fastq SRR35012817_2.fastq

mamba install multiqc 
 multiqc outqc 


cp -r multiqc_report.html /mnt/c/Users/moli/Downloads/