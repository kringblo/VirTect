## VirTect


Virtect is a software that detected virus from RNA-Seq on human samples.


## Introduction

VirTect is an efficient software tool for virus detection. Virtect take NGS data as a input in FASTQ format and mapped to human reference genome using tophat. After subtraction of non-human sequence from the human sequence, VirTecst used bwa-men command to align the non-human sequence to our defined 757 different virus database to report the virus. After alignment of non-human sequence to virus database, VirTect do the filtrations to discriminate the viral sequence from the noise or artifact and finally report the real viruses. 

Here is an example that how VirTect works, for the HCC sample, we have about 53 million paired reads,. VirTect mapped about 51 of 53 million reads (about 96.7%) to human reference and subtracted the remaining about 2 million, the non-human reads from the human sequence. Then VirTect mapped the non-human sequence to virues geomes, before filtrations, thousands of reads are mapped to different viruses in our defined virus database such as mapped to tick borne encephalitis, hepatitis C, cutthroat trout, and hepatitis B etc., however, only hepatitis B passed our filtrations. Also we examined some of the virus, which did not pass our filtrations, however significant number of non-human reads mapped to them and we found that it is not a real viral sequence, however, it is mapped to poly(A) sequence of hepatitis C genotype 1.


This is the GitHub repository for the documentation of the VirTect software, described in the paper listed below. If you like this repository, please click on the "Star" button on top of this page, to show appreciation to the repository maintainer. If you want to receive notifications on changes to this repository, please click the "Watch" button on top of this page.

## Dependency

First we need to install the following publicly available tools to run the VirTect:


tophat (https://ccb.jhu.edu/software/tophat/index.shtml)

bwa (http://bio-bwa.sourceforge.net/bwa.shtml) 

samtools (http://samtools.sourceforge.net/)

bedtools (http://bedtools.readthedocs.io/en/latest/)

## Installation

Please clone the repository into your computer:

    git clone https://github.com/WGLab/VirTect

Then enter VirTect directory:

    cd VirTect

## Synopsis

    python VirTect.py --help

    python VirTect.py -1 Reads_1.fq -2 Reads_2.fq -o Test -ucsc_gene data/gencode.v25.chr_patch_hapl_scaff.annotation.gtf -index data/hg38 -index_vir data/viruses_757.fasta -t 8


## License Agreement

By using the software, you acknowledge that you agree to the terms below:

For academic and non-profit use, you are free to fork, download, modify, distribute and use the software without restriction.
 
 ## Contact
Atlas Khan (ak4046@cumc.columbia.edu)

Kai Wang (kw2701@cumc.columbia.edu)

## Reference

Khan A, Stucky A, Parish P. Sedghizadeh, Zhang Xi, Wang K, Zhong JF, **Detection of viral infection in cancer and its application to HPV Induced Head and Neck Squamous Cell Carcinoma**, In preparation. 


## More information
Wang Genomics Lab Homepage (http://wglab.org/)
