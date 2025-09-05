# Chapter 3 - Trimming and assembly!

## Trimming
Adapter trimming and quality filtration are very important steps of QC, and are required before performing further downstream processing. Since you downloaded 2 FASTQ isolates from your exercise, we'll use them to perform trimming using two different tools!

**Step 1.** We'll firstly install both fatsp and trim-galore. Remember, you can install multiple in a single command
<pre> mamba install -c bioconda fastp trim-galore -y </pre>
#### Tip: Using the `-y` flag in the command ensures that you don't need to confirm your download, as you have already specified it here.

**Step 2.** Now, we'll firstly use `fastp` to trim our isolates. Firstly, we'll create a new dir called `trim`, we'll be storing our trimmed files there.
In case you forgot, the command is `mkdir trim`

<pre> fastp -i raw_data/SRR35160851_1.fastq -I raw_data/SRR35160851_2.fastq -o trim/SRR35160851.1_trimmed.fastq -O trim/SRR35160851.2_trimmed.fastq --cut_front --cut_tail --cut_window_size 4 --detect_adapter_for_pe --qualified_quality_phred 20 --length_required 30 --thread 2 </pre>

#### As you can see, this is a long command! What `-i` and `-I` signify are the input options, `-i` will ALWAYS be the _1 or _R1 file, `-I` will ALWAYS be the _2 or _R2 file. Similarly, `-o` and `-O` are to signify the output name. In order to maintain consistency, we keep the names same, just adding _trimmed somewhere so it's easy to recognise. `--cut_front` and `--cut_tail` flags create a sliding window of 4 bases, which we have specified using `--cut_window_size 4` flag. `--detect_adapter_for_pe` allows fastp to detect adapter sequences automatically for both files and remove them. `--qualified_quality_phred 20` is the PHRED quality threshold that we have set. In the same way, `--length_required 30` is the threshold for length in our tool. `--thread 2` is to provide 2 threads to trim, which will hurry up the process.

Now, we'll trim our second file using `trim_galore`. The command that we'll use is as follows:
<pre> trim_galore -j 2 -o trim/SRR35160860 --length 30 -q 20 --paired raw_data/SRR35160860_1.fastq raw_data/SRR35160860_2.fastq </pre>

#### Here, the `-j` flag is to specify threads, `-q` and `--length` are to set PHRED quality and length thresholds, `-o` sets the output directory, in which the trimmed files are stored. `--paired` is used to tell `trim_galore` that you are inputting two files.

Now that we have finisheed trimming, we'll move on to the next important step: genome assembly.

## Genome assembly
Genome assembly is, at its simplest, the process of reconstructing the complete DNA sequence of an organism’s genome from the short fragments (FASTQ reads) into a continous sequence.

We'll be performing de-novo genome assembly of our 2 isolates, using `spades` for it.
**Step 1.** Install using:
<pre> mamba install -c bioconda spades -y </pre>

**Step 2.** Now, run `spades` using the following command
<pre> spades.py -1 trim/SRR35160851.1_trimmed.fastq -2 trim/SRR35160851.2_trimmed.fastq -o SRR35160851_spades -t </pre>
<pre> spades.py -1 trim/SRR35160860/SRR35160860_1_val_1.fq -2 trim/SRR35160860/SRR35160860_2_val_2.fq -o SRR35160860_spades -t 2 </pre>

Genome assembly is a time taking process, so sit back and relax and it should be done in some time.
