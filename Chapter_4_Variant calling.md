# Chapter 3 - Trimming and assembly!



mamba install spades 
 

use val file 1 and 2 

spades.py -1 SRR26048983_1_val_1.fq -2 SRR26048983_2_val_2ls
.fq -o trim/




mamba install bwa 

mamba install samtools 

bwa index  GCF_900475035.1_41965_F01_genomic.fna

bwa mem GCF_900475035.1_41965_F01_genomic.fna trim/SRR26048983_1_val_1.fq trim/SRR26048983_2_val_2.fq > output.samlsls

samtools view -bS output.sam > output.bam

samtools sort -o sorted.bam output.bam


mamba install quast 
quast -t 2 -r GCF_900475035.1_41965_F01_genomic.fna spades/scaffolds.fasta -o outresults 


mamba install picard 
picard MarkDuplicates -I sorted.bam -O dedup.bam -M metrics.txt --CREATE_INDEX true


mamba install freebayes
freebayes-parallel <(fasta_generate_regions.py ref/GCF_900475035.1_41965_F01_genomic.fna.fai 100000) 2 -f ref/GCF_900475035.1_41965_F01_genomic.fna dedup.bam > variants.vcf






