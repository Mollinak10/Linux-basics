Hi everyone 👋 We'll start with lesson 3️⃣   
Today We'll learn how to do Fastqc and Multiqc.   
⚠️Make sure that you are working in a fresh directory before starting. ⚠️

In the previous lesson, we learned how to set up and work within a virtual environment. Since we now need to download tools, please follow the steps below.

**Installing fastqc**

<pre>mamba install bioconda::fastqc -y</pre>     
➡️ To check whether the tool is properly installed 
<pre>fastqc --version</pre>  
➡️ A message like the one below will appear with details about the version as well.   
<pre>FastQC v0.12.1</pre>

**Installing SRA tools**

Step 1.   
<pre>mamba install sra-tools </pre>  

1. To download SRA files use this link https://www.ncbi.nlm.nih.gov/sra   
2. You can type your organism's name and click on the first link that the search provides. 
3. Check wether the file name starts with SRR and just copy it for the next step. 
4. Also check what type the file is paired/unpaired. 

Step 2.   
<pre> prefetch SRR35012817</pre>   

Step 3.   
➡️ If the file is not paired
<pre>fastq-dump SRR35012817</pre>    

➡️ If the file is paired  
<pre>fastq-dump --split-files SRR35012817</pre>    
You'll get two .fastq files since it is a paired file    


Step 4.   
Make a new directory to keep the results of the previous steps. *make another directory outqc*  
<pre>mkdir QC </pre>
<pre>mv *.fastq QC </pre> 
➡️ mv will move your fastq files to outqc   

Step 5.     
<pre>fastqc -o outqc/ SRR35012817_1.fastq SRR35012817_2.fastq</pre>

Step 6. Install multiqc to generate a report 

<pre>mamba install multiqc</pre>
<pre>multiqc outqc </pre>    
 Step 7. 
<pre>cp -r multiqc_report.html /mnt/c/Users/moli/Downloads/</pre>

⚠️/mnt/c/Users/ and /Downloads/ is common for every user but /moli/ is the path in my system and different for everyone. ⚠️



