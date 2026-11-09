BBD Metagenome: Gene Annotation
================
Kaytlin Edwards
2026-11-09

# Step 7: Gene Annotation with Prokka

Prokka was used to identify genes within the 14 selected metagenomic
bins and predict their possible functions. It does this by comparing the
identified gene sequences with previously characterised genes and their
known functions. This provides a better understanding about what
microorganisms, associated with black band disease, may be capable of
doing.

``` bash
# Test Prokka on one selected bin
cd ~/bbd-metagenome/prokka

bin=metabat.5
prokka --cpus 2 --outdir $bin --prefix $bin ../metabat/bins_bbd/${bin}.fa

# Examine the annotation files
ls metabat.5
```

## Annotating All Selected Bins

After Prokka was successfully tested on one bin, a SLURM job was
submitted to identify and annotate genes across all 14 selected
metagenomic bins.

``` bash
# Submit Prokka job
cd ~/bbd-metagenome/prokka
sbatch run_prokka.sh

# Check job status
squeue -u $USER
```

``` bash
# Check Prokka job completion
sacct -j 624 --format=JobID,State,ExitCode

# Examine annotation results
cd ~/bbd-metagenome/prokka
ls metabat.26
head -n 10 metabat.26/metabat.26.tsv
```

The Prokka analysis completed successfully and produced annotation files
for the 14 bibns that contain predicted gene names and function. These
included predicted genes with known functions, as well as hypothetical
proteins because their function could not be determined.
