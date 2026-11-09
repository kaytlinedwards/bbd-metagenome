# The Metagenome of Black Band Disease

### Background

This project investigates the microbial community associated with Black Band Disease (BBD) in *Acrapora hyacinthis* corals collected from Orpheus Island on the Great Barrier Reef in 2023. Black Band Disease is a coral disease involving a complex microbial community that contributes to coral tissue degradation. Using the DNA sequences obtained via Oxford Nanopore sequencing, we will assemble the metagenome, identify the specific bacteria that is present, and examine their genes and metabolic pathways to better understand their potential contributing roles in the BBD.

This analysis was done for [Workshop 4](https://mb5370.bioinformatics.guide/workshop4.html) of the MB5370 Marine Genomics module, at James Cook University in 2026.

## Analysis

```{=html}
<!--
Each link opens the knitted version of one RMarkdown file. Knit each .Rmd,
then add both the .md file and its _files folder (if there is one) to git.
-->
```

1.  [Assembly](01_assembly.md)
2.  [Binning](02_binning.md)
3.  [Bin quality](03_bin_quality.md)
4.  [Taxonomy](04_taxonomy.md)
5.  [Gene annotation](05_gene_annotation.md)
6.  [Metabolic pathways](06_metabolic_pathways.md)

## Repository layout

Each step has a numbered RMarkdown file at the top of the repository and a folder where its commands are run.

| Step               | Notes                       | Folder     | Tool      |
|--------------------|-----------------------------|------------|-----------|
| Assembly           | `01_assembly.Rmd`           | `flye/`    | Flye      |
| Binning            | `02_binning.Rmd`            | `metabat/` | MetaBAT 2 |
| Bin quality        | `03_bin_quality.Rmd`        | `checkm/`  | CheckM    |
| Taxonomy           | `04_taxonomy.Rmd`           | `gtdbtk/`  | GTDB-Tk   |
| Gene annotation    | `05_gene_annotation.Rmd`    | `prokka/`  | Prokka    |
| Metabolic pathways | `06_metabolic_pathways.Rmd` | `minpath/` | MinPath   |

`index.Rmd` joins all six steps into one web page. Knit it to make `index.html`.
