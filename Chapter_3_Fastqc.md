# Starting with basic file processing and QC

Hi everyone 👋 We'll start with lesson 3️⃣   
Today We'll learn how to do Fastqc and Multiqc.   
⚠️Make sure that you are working in a fresh directory before starting. ⚠️

In the previous lesson, we learned how to set up and work within a virtual environment. Since we now need to download tools, please follow the steps below.

**Installing fastqc**

<pre> mamba install bioconda::fastqc -y </pre>
➡️ To check whether the tool is properly installed 
<pre>fastqc --version</pre>  
➡️ A message like the one below will appear with details about the version as well.   
<pre>FastQC v0.12.1</pre>

**Installing SRA tools**

Step 1.   
<pre>mamba install sra-tools </pre>  

1. To download SRA files use SRA database (https://www.ncbi.nlm.nih.gov/sra).   
2. Type in your organism's name and search, you'll get a comprehensive list of results.
3. Click on an experiment to open up its page, and peek into all the information about the experiment. 
4. The SRR ID is given at the bottom, and simply copy it for the next step. 
5. Additionally, check for the type of technology and layout used! It's important for later steps since we are working on Illumina short reads, which usually have a **paired** layout. 

Step 2. Retrieve your file using the following command, `prefetch` is a command of sra-tools.
<pre> prefetch SRR35012817</pre>   

Step 3. Now that we have retrieved our file, it's still not in the FASTQ format, we need to extract is using the following command:
➡️ If the file is **not** in **paired** layout
<pre>fasterq-dump SRR35012817/SRR35012817.sra</pre>    

➡️ If the file is in **paired**  
<pre> fasterq-dump --split-files SRR35012817/SRR35012817.sra </pre>    
You'll get two **FASTQ** files since it is a paired-end file.

Step 4. We'll create a new dir called raw_data and store our raw FASTQ files into that.
<pre> mv *.fastq raw_data </pre>
➡️ mv will move your fastq files to raw_data

Step 5. Make a new directory in which we'll store the results of our QC. 
<pre> mkdir QC </pre> 

Step 6. Now, we'll run FASTQC on our raw_data
<pre>fastqc -o QC raw_data/SRR35012817_1.fastq raw_data/SRR35012817_2.fastq</pre>

Step 7. Install multiqc to generate a report of both the files for easier viewing. 

<pre>mamba install multiqc</pre>
<pre>multiqc QC </pre>    
 
Step 8. Since our file is in the HTML format, we'll need to visualise it in a browser. If you cannot access your Ubuntu home dir then you can simply copy your report to an easily accessible location such as the Downloads or the Desktop. We'll copy it to the Downloads dir.
<pre> cp multiqc_report.html /mnt/c/Users/moli/Downloads/ </pre>

⚠️/mnt/c/Users/ and /Downloads/ is common for every user but /moli/ is the path in my system and will be different for everyone. You can double-tap the Tab button when typing in your path till the Users bit. ⚠️

#### Exercise: Download multiple SRA files (all are Illumina paired-end sequences) SRR35160851 and SRR35160860, extract them, run FASTQC on them and create a multiqc report.

