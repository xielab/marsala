# marsala
Welcome to marsala. <br />
The main site was http://xielab.github.io/marsala

## What is Marsala?
Marsala is a program that comprehensively detects variants (SNV and CNV) in PGS with linkage analysis. Marsala runs on Linux.

## What types of input can I use with Marsala?

Marsala is designed to work with reads from whole genome sequencing, although users have been successful in using Marsala with reads from specific region of genome.

In general, Marsala uses sequencing information from three parts:

1. Disease-Grandparent or Disease-child (A)

2. Disease-parent (F)

3. Embryo (E)

In addition, users can use sequencing information from polar body 1 (PB1) and polar body 2 (BP2) that corresponds to specific embryo, which will make result more accurate.

## How does Marsala detect variants?

1. SNV <br />
First, given specific genomic region (less than 2Mbp) Marsala detects SNVs for A, F and E (as well as PB1 and PB2) seperately. <br />
Then, Marsala compares the genotypes between A amd F and infer which one of the chromosome homologous was passed from A to F. (i.e. risk genomic mate determination) <br />
Next, Marsala compares the genotypes between F and E and estimate the ratio of risk passed sites to all passed sites. <br />
Finally, Marsala determines whether this E obtains the risk genomic region which contains disease-related mutation. <br />

2. CNV <br />
Marsala estimate the DNA copy number of E and report whether E was normal.

This protocol has been validated in following research: <br />

Liying Yan,  Lei Huang,  Liya Xu,  Jin Huang,  Fei Ma,  Xiaohui Zhu,  Yaqiong Tang,  Mingshan Liu, Ying Lian,  Ping Liu,  Rong Li,  Sijia Lu,  Fuchou Tang,  Jie Qiao,   X. Sunney Xie.  Live births after simultaneous avoidance of monogenic diseases and chromosome abnormality by next-generation sequencing with linkage analyses.PNAS 2015 112 (52) 15964-15969

## Prerequisites

To use marsala, you will need the following programs in your PATH:

bwa <br />
http://bio-bwa.sourceforge.net/

samtools [equal or older than v1.2] <br />
http://samtools.sourceforge.net/

bcftools <br />
https://samtools.github.io/bcftools/

GATK <br />
https://www.broadinstitute.org/gatk/

control-freec <br />
http://bioinfo-out.curie.fr/projects/freec/

## Obtaining and intalling Marsala

You can download the latest source release on github.

To install marsala, unpack the tarball and change directory to the package directory as follows:

`tar zxvf marsala-0.0.1.tar.gz`

`cd marsala-0.0.1`

Configure the package, specifying the install path of required tools as needed

`./configure`

## Using Marsala

Please just type marsala for detail help.


