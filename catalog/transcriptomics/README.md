# Transcriptomics Analysis Pipelines

## Overview

Transcriptomics pipelines for RNA sequencing (RNA-seq) data analysis, including bulk RNA-seq, single-cell RNA-seq (scRNA-seq), and specialized RNA analysis methods.

## Available Pipelines

### 1. Bulk RNA-seq Differential Expression Analysis
**Description**: Quantifies gene expression levels and identifies differentially expressed genes between conditions.

**Key Tools**:
- STAR or HISAT2: RNA-seq alignment
- featureCounts or HTSeq: Read counting
- DESeq2 or edgeR: Differential expression analysis
- Salmon or Kallisto: Transcript quantification (alignment-free)

**Input**: FASTQ files
**Output**: Count matrices, differential expression results, normalized expression values

**Workflow Steps**:
1. Quality control and adapter trimming
2. Alignment to reference genome or transcriptome
3. Read counting or pseudo-alignment
4. Normalization
5. Differential expression testing
6. Multiple testing correction
7. Functional enrichment analysis

### 2. Single-Cell RNA-seq Analysis
**Description**: Analyzes gene expression at single-cell resolution for cell type identification and trajectory analysis.

**Key Tools**:
- Cell Ranger: 10X Genomics data processing
- Seurat or Scanpy: scRNA-seq analysis framework
- Monocle: Trajectory inference
- Harmony or Scanorama: Batch correction

**Input**: FASTQ files or count matrices
**Output**: Cell clusters, markers, UMAP/tSNE visualizations

**Workflow Steps**:
1. Cell barcode and UMI processing
2. Quality filtering (doublet removal, low-quality cells)
3. Normalization and feature selection
4. Dimensionality reduction (PCA, UMAP, t-SNE)
5. Clustering and cell type annotation
6. Differential expression by cluster
7. Trajectory and pseudotime analysis

### 3. Alternative Splicing Analysis
**Description**: Identifies and quantifies alternative splicing events and isoform switching.

**Key Tools**:
- rMATS: Alternative splicing detection
- SUPPA2: Splicing analysis from RNA-seq
- LeafCutter: Intron excision quantification
- IsoformSwitchAnalyzeR: Isoform switching detection

**Input**: Aligned BAM files or junction files
**Output**: Splicing event quantification, differential splicing results

### 4. Long Non-coding RNA (lncRNA) Analysis
**Description**: Identifies and characterizes long non-coding RNAs from RNA-seq data.

**Key Tools**:
- FEELnc: lncRNA prediction
- CPAT: Coding potential assessment
- LNCipedia: lncRNA database

**Input**: Assembled transcripts (GTF/GFF)
**Output**: Annotated lncRNA catalog

### 5. Gene Fusion Detection
**Description**: Identifies fusion transcripts from RNA-seq data, particularly relevant in cancer studies.

**Key Tools**:
- STAR-Fusion: Gene fusion detection
- Arriba: Fast fusion detection
- FusionCatcher: Comprehensive fusion caller

**Input**: FASTQ files
**Output**: List of fusion events with supporting reads

### 6. Transcript Assembly and Quantification
**Description**: Reconstructs full-length transcripts and quantifies isoform expression.

**Key Tools**:
- StringTie: Transcript assembly and quantification
- Cufflinks: Transcript assembly
- RSEM: RNA-seq quantification

**Input**: Aligned BAM files
**Output**: Assembled transcripts (GTF), abundance estimates

## Data Requirements

- **Sequencing Depth**:
  - Bulk RNA-seq: 20-30M reads per sample
  - scRNA-seq: 50,000-100,000 reads per cell
  - Differential expression: 3+ biological replicates
- **Read Length**: Paired-end 75-150bp preferred
- **RNA Quality**: RIN score ≥7 for bulk RNA-seq

## Best Practices

1. Use biological replicates for differential expression
2. Check for batch effects and confounding factors
3. Validate expression patterns using qRT-PCR
4. Consider library preparation bias (e.g., poly-A vs. rRNA depletion)
5. Use appropriate normalization methods for cross-sample comparison

## Use Cases

- Disease biomarker discovery
- Drug response profiling
- Developmental biology studies
- Cancer transcriptome characterization
- Cell type identification and characterization
- Gene regulatory network inference

## References

- Dobin et al. (2013). STAR: ultrafast universal RNA-seq aligner. Bioinformatics.
- Love et al. (2014). Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2. Genome Biology.
- Hao et al. (2021). Integrated analysis of multimodal single-cell data. Cell.
- Pertea et al. (2015). StringTie enables improved reconstruction of a transcriptome from RNA-seq reads. Nature Biotechnology.
