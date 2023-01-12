# Filter
With this script, filter the reads who align to the BuGZSAM haplotype in a manner that is completely male specific, start common end male specific, or start specific end common.
Then, we write these reads in a Fasta file, which, givinf this as the  bowtie2/minimap2 input will give you a new alignment only for the filtered sequences!

Bowtie2 alignment is by:
- bowtie2 -p 64 -f -a --no-unal --ignore-quals -x <indexprefix> -U <input.fa> -S <output.sam>
        -a so that it searches for all distinct, valid alignments for each read
        -f so that it nows the given input files are fasta
        --ignore-quals to consider the quality value as max, so that bowtie2 doesn't check quality values
