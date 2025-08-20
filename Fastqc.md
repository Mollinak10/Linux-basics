Hi everyone 👋 we'll start with lesson 3️⃣ 
We'll learn how to do Fastqc. 
First of all make a directory and work in that. 

In the previous lesson, we learned how to set up and work within a virtual environment. Since we now need to download tools, please follow the steps below.

**Installing fastqc**

<pre>mamba install bioconda::fastqc -y</pre>     
To check whether the tool properly installed 
<pre>fastqc --version</pre>  
and you will see a message like this appear with details about the version as well.   
<pre>FastQC v0.12.1</pre>

**Installing SRA tools**

Step 1. <pre>mamba install sra-tools </pre>  

To download SRA files use this link https://www.ncbi.nlm.nih.gov/sra   
You can type your organism's name and click on the first link that the search provides. 
Check wether the file name starts with SRA or SRR and just copy it for the next step. 
Also check what type the file is paired/unpaired. 

Step 2. <pre> prefetch SRR35012817</pre>   

Step 3. If the file is not paired
<pre>fastq-dump SRR35012817</pre>    

If the file is paired  
<pre>fastq-dump --split-files SRR35012817</pre> 


mkdir outqc 
mv *.fastq 



fastqc -o outqc/ SRR35012817_1.fastq SRR35012817_2.fastq

mamba install multiqc 
 multiqc outqc 



cp -r multiqc_report.html /mnt/c/Users/moli/Downloads/
