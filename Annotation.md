Annotation lesson 5 


mamba install prokka

prokka --outdir prokka --prefix molly --addmrna --addgenes --locustag PROKKA --cpus 2 --notrna --norrna spades/contigs.fasta


faa amino acid 
fna fasta nucleotide 
gbf annotation table formats 


ls
cd prokka
ls
molly.err  molly.ffn  molly.fsa  molly.gff  molly.sqn  molly.tsv
molly.faa  molly.fna  molly.gbk  molly.log  molly.tbl  molly.txt





mamba install ncbi-amrfinderplus

amrfinder -u

amrfinder

amrfinder --list_organisms

amrfinder --protein prokka/molly.faa --organism Streptococcus_pyogenes --output amr.txt --threads 2

nano amr.txt

amrfinder --nucleotide spades/contigs.fasta --organism Streptococcus_pyogenes --output amr.txt --threads 2
 
nano amr.txt 

