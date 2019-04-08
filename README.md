# ![nf-core/chipseq](docs/images/nfcore-chipseq_logo.png)

[![Build Status](https://travis-ci.org/nf-core/chipseq.svg?branch=master)](https://travis-ci.org/nf-core/chipseq)
[![Nextflow](https://img.shields.io/badge/nextflow-%E2%89%A50.32.0-brightgreen.svg)](https://www.nextflow.io/)

[![install with bioconda](https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/)
[![Docker](https://img.shields.io/docker/automated/nfcore/chipseq.svg)](https://hub.docker.com/r/nfcore/chipseq/)

## Introduction
**nfcore/chipseq** is a bioinformatics analysis pipeline used for Chromatin ImmunopreciPitation sequencing (ChIP-seq) data.

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It comes with docker containers making installation trivial and results highly reproducible.

### Pipeline Steps

* Make BWA reference genome index (optional)
* Build BED reference based on GTF (optional)
* FastQC for initial quality control of sequence reads
* TrimGalore! for adapter trimming
* BWA for alignment
* Samtools for post-alignment processing with and alignment statistics
* Picard MarkDuplicates for duplicate removal
* Count read statistics
* Phantompeakqualtools for NSC, RSC and strand-shift cross correlation plot
* DeepTools for paired-end fragment size distribution, fingerprint, reads distribution profile, sample pair-wise correlation, and PCA plot
* MACS2 for peak calling
* MACS2 for Saturation analysis (optional)
* Bioconductor ChIPpeakAnno for peak annotation and blacklisted regions filtering which is optional
* MultiQC

### Documentation
The nf-core/chipseq pipeline comes with documentation about the pipeline, found in the `docs/` directory:

1. [Installation](https://nf-co.re/usage/installation)
2. Pipeline configuration
    * [Local installation](https://nf-co.re/usage/local_installation)
    * [Adding your own system config](https://nf-co.re/usage/adding_own_config)
    * [Reference genomes](https://nf-co.re/usage/reference_genomes)
3. [Running the pipeline](docs/usage.md)
4. [Output and how to interpret the results](docs/output.md)
5. [Troubleshooting](https://nf-co.re/usage/troubleshooting)

## Credits
These scripts were written for use at the [National Genomics Infrastructure](https://portal.scilifelab.se/genomics/)
at [SciLifeLab](http://www.scilifelab.se/) in Stockholm, Sweden.
Written by Chuan Wang ([@chuan-wang](https://github.com/chuan-wang)) and Phil Ewels ([@ewels](https://github.com/ewels)).
