mkdir long_reads/
ls
prefetch ERR15424202	

fasterq-dump ERR15424202/ERR15424202.sra

mamba create -name long_reads

# Downloading Kraken2 db 
wget https://genome-idx.s3.amazonaws.com/kraken/k2_standard_08_GB_20250714.tar.gz 
# Extracting db
tar -xzvf k2_standard_08_GB_20250714.tar.gz

# Now we'll run Kraken2
kraken2 --db db/ --threads 2 --memory-mapping --use-names \
--gzip-compressed ERR.fastq --report ER.kreport --output ER.kraken

# Now we'll visualize using Krona!

ktImportTaxonomy -t 3 -m 5 -o krona.html ER.kreport

