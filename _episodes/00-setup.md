---
title: "Setup"
teaching: 15
exercises: 0
questions:
objectives:
- "Download and install relevant files and programmes"
keypoints:
---

# Download transcriptome

Today's practical will use the yeast transcriptome. Navigate to your target folder and use the command to download the file.

```
wget "ftp://ftp.ensembl.org/pub/release-95/fasta/saccharomyces_cerevisiae/cdna/Saccharomyces_cerevisiae.R64-1-1.cdna.all.fa.gz"
```

# Download RNA-seq data

The RNA-seq data that we will be using is hosted at NCBI's Sequence Read Archive (SRA). The NCBI SRA Toolkit "enables reading ("dumping") of sequencing files from the SRA database and writing ("loading") files into the .sra format". You can read more about it and the tools it contains: https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc

```
sudo apt-get install sra-toolkit
```

Once installed, execute the following command to download the data of 6 RNA-seq runs from the same experiment that we will use in this tutorial.

```
for id in SRR4018567 SRR4018568 SRR4018569 SRR4018573 SRR4018574 SRR4018575
do
  fastq-dump --split-files $id
done
```
