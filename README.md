# Snakemake workflow: rna-seq-star-deseq2

This workflow performs a differential expression analysis with STAR and Deseq2.

## Usage

### Simple

#### Step 1: Install workflow
git clone this repo

#### Step 2: Configure workflow

Configure the workflow according to your needs via editing the file `config.yaml`.

#### Step 3: Execute workflow
create a conda env
```
conda create -n StarDESeq2 r-base=3.4.1 bioconductor-deseq2=1.18.1 bioconductor-annotate=1.56.0 bioconductor-annotationdbi=1.40.0 bioconductor-biobase=2.38.0 bioconductor-biocgenerics=0.24.0 bioconductor-biocparallel=1.12.0 bioconductor-delayedarray=0.4.1 bioconductor-genefilter=1.60.0 bioconductor-geneplotter=1.56.0 bioconductor-genomeinfodb=1.14.0 bioconductor-genomeinfodbdata=1.0.0 bioconductor-genomicranges=1.30.0 bioconductor-iranges=2.12.0 bioconductor-s4vectors=0.16.0 bioconductor-summarizedexperiment=1.8.0 bioconductor-tximport=1.6.0 bioconductor-xvector=0.18.0 bioconductor-zlibbioc=1.24.0 r-acepack=1.4.1 r-backports=1.0.5 r-base64enc=0.1_3 r-bh=1.65.0_1 r-bit=1.1_12 r-bit64=0.9_5 r-bitops=1.0_6 r-blob=1.1.0 r-catools=1.17.1 r-checkmate=1.8.2 r-cluster=2.0.6 r-colorspace=1.3_2 r-dbi=0.6_1 r-dichromat=2.0_0 r-digest=0.6.12 r-evaluate=0.10 r-foreign=0.8_67 r-formula=1.2_1 r-futile.logger=1.4.3 r-futile.options=1.0.0 r-gdata=2.17.0 r-getopt=1.20.0 r-ggplot2=2.2.0 r-gplots=3.0.1 r-gridextra=2.2.1 r-gtable=0.2.0 r-gtools=3.5.0 r-highr=0.6 r-hmisc=4.0_3 r-htmltable=1.9 r-htmltools=0.3.6 r-htmlwidgets=0.9 r-jsonlite=1.4 r-kernsmooth=2.23_15 r-knitr=1.16 r-labeling=0.3 r-lambda.r=1.1.9 r-lattice=0.20_34 r-latticeextra=0.6_28 r-lazyeval=0.2.0 r-locfit=1.5_9.1 r-magrittr=1.5 r-markdown=0.8 r-mass=7.3_45 r-matrix=1.2_7.1 r-matrixstats=0.52.2 r-memoise=1.1.0 r-mime=0.5 r-munsell=0.4.3 r-nnet=7.3_12 r-pkgconfig=2.0.1 r-plogr=0.1_1 r-plyr=1.8.4 r-rcolorbrewer=1.1_2 r-rcpp=0.12.13 r-rcpparmadillo=0.7.800.2.0 r-rcurl=1.95_4.8 r-reshape2=1.4.2 r-rjson=0.2.15 r-rlang=0.1.2 r-rpart=4.1_10 r-rsqlite=2.0 r-scales=0.4.1 r-snow=0.4_2 r-stringi=1.1.2 r-stringr=1.2.0 r-survival=2.40_1 r-tibble=1.3.3 r-viridis=0.4.0 r-viridislite=0.2.0 r-xml=3.98_1.6 r-xtable=1.8_2 r-yaml=2.1.14  rseqc=3.0 pandas=0.23 gffutils=0.9
```

Test your configuration by performing a dry-run via

    snakemake -n

Execute the workflow locally via

    snakemake --cores $N

using `$N` cores or run it in a cluster environment via

    snakemake --cluster qsub --jobs 100

or

    snakemake --drmaa --jobs 100

# Step 4: Investigate results

After successful execution, you can create a self-contained interactive HTML report with all results via:

    snakemake --report report.html

This report can, e.g., be forwarded to your collaborators.
An example (using some trivial test data) can be seen [here](https://cdn.rawgit.com/snakemake-workflows/rna-seq-star-deseq2/master/.test/report.html).


## Testing

Tests cases are in the subfolder `.test`. They are automtically executed via continuous integration with Travis CI.
