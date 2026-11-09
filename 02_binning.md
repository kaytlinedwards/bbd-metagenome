BBD Metagenome: Binning
================
Kaytlin Edwards
2026-11-09

## Step 2: Metagenome Binning with MetaBAT2

The assembled DNA sequences were grouped into bins using MetaBAT2.
Before running MetaBAT2, the coverage information was obtained from the
Flye assembly results, and the contigs were reordered to match this
information. MetBAT2 then grouped the contigs based on similarities in
their sequence composition and coverage. The analysis produced 71 bins
containing ~39.9 million DNA bases in total. Each bin represents a group
of contigs predicted to originate from the same microbial genome.
However the quality of these bins still needs to be assessed next before
it can be used for further analysis.

Binning of the assembled contigs into genomes with MetaBAT 2. Commands
for this step were run in `metabat/`.

``` bash

cd ~/bbd-metagenome/metabat

# Prepare coverage/depth information
cat ../flye/bbd/assembly_info.txt | grep -v '#' | awk 'BEGIN{OFS="\t"}{print $1,$3}' > depths_bbd.txt

# Inspect depth file
head depths_bbd.txt

# Reorder contigs
awk '{print $1}' depths_bbd.txt | xargs samtools faidx ../flye/bbd/assembly.fasta > assembly_bbd_ordered.fasta

# Check reordered assembly
ls -lh assembly_bbd_ordered.fasta

# Run MetaBAT2
metabat2 -i assembly_bbd_ordered.fasta -a depths_bbd.txt --cvExt -o bins_bbd/metabat --seed 5

# Inspect generated bins
ls bins_bbd*
```
