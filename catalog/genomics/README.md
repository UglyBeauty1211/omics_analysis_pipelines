# Genomics Analysis Pipelines

## Overview

Genomics analysis pipelines for processing and analyzing genome-scale DNA sequencing data, including whole genome sequencing (WGS), whole exome sequencing (WES), and targeted sequencing approaches.

## Available Pipelines

### 1. Variant Calling Pipeline
**Description**: Identifies single nucleotide variants (SNVs) and insertions/deletions (indels) from aligned sequencing reads.

**Key Tools**:
- BWA or Bowtie2: Read alignment
- SAMtools: BAM file processing
- GATK or FreeBayes: Variant calling
- VCFtools: VCF filtering and manipulation

**Input**: FASTQ files (paired-end or single-end)
**Output**: VCF files with annotated variants

**Workflow Steps**:
1. Quality control (FastQC)
2. Read trimming and filtering
3. Reference genome alignment
4. Duplicate marking
5. Base quality score recalibration
6. Variant calling
7. Variant filtering and annotation

### 2. Structural Variation Detection
**Description**: Identifies large-scale genomic rearrangements including deletions, duplications, inversions, and translocations.

**Key Tools**:
- Manta, Delly, or Lumpy: SV detection
- Sniffles: Long-read SV calling
- SURVIVOR: SV merging and filtering

**Input**: Aligned BAM files
**Output**: VCF files with structural variants

### 3. Copy Number Variation (CNV) Analysis
**Description**: Detects and quantifies copy number variations across the genome.

**Key Tools**:
- CNVkit: CNV detection from targeted sequencing
- Control-FREEC: Copy number and allelic content
- PURPLE: Somatic copy number caller

**Input**: Tumor/normal BAM files
**Output**: CNV segments and plots

### 4. Genome Assembly Pipeline
**Description**: De novo genome assembly from short or long sequencing reads.

**Key Tools**:
- SPAdes or MaSuRCA: Short-read assembly
- Flye or Canu: Long-read assembly
- QUAST: Assembly quality assessment

**Input**: FASTQ files
**Output**: Assembled contigs/scaffolds (FASTA)

### 5. Genome Annotation
**Description**: Identifies and annotates genes, regulatory elements, and other genomic features.

**Key Tools**:
- MAKER or Augustus: Gene prediction
- BLAST: Homology-based annotation
- InterProScan: Functional annotation

**Input**: Genome assembly (FASTA)
**Output**: GFF3/GTF annotation files

## Data Requirements

- **Sequencing Depth**: 
  - WGS: 30-60X coverage
  - WES: 100-150X coverage
  - Targeted: 500-1000X coverage
- **Read Quality**: Phred score ≥30 for >90% of bases
- **Reference Genome**: Species-appropriate reference assembly

## Best Practices

1. Always perform quality control on raw sequencing data
2. Use appropriate reference genome version
3. Apply filtering criteria based on sequencing platform and depth
4. Validate critical variants using orthogonal methods
5. Consider batch effects in multi-sample studies

## Use Cases

- Rare disease diagnosis
- Cancer genomics and precision medicine
- Population genetics studies
- Agricultural genomics and breeding
- Evolutionary genomics

## References

- McKenna et al. (2010). The Genome Analysis Toolkit. Genome Research.
- Li & Durbin (2009). Fast and accurate short read alignment with Burrows-Wheeler transform. Bioinformatics.
- DePristo et al. (2011). A framework for variation discovery and genotyping using next-generation DNA sequencing data. Nature Genetics.
