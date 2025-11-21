# Epigenomics Analysis Pipelines

## Overview

Epigenomics pipelines for analyzing DNA modifications, chromatin structure, and histone modifications that regulate gene expression without altering the DNA sequence.

## Available Pipelines

### 1. DNA Methylation Analysis (BS-seq/WGBS)
**Description**: Analyzes whole-genome bisulfite sequencing data to quantify DNA methylation at single-base resolution.

**Key Tools**:
- Bismark: BS-seq alignment and methylation calling
- BSseeker2/3: Bisulfite mapping and methylation calling
- MethylDackel: Methylation extraction
- methylKit: Differential methylation analysis
- DSS: Dispersion shrinkage for sequencing data

**Input**: Bisulfite-converted sequencing reads (FASTQ)
**Output**: Methylation levels (CpG, CHG, CHH contexts), differentially methylated regions (DMRs)

**Workflow Steps**:
1. Quality control and adapter trimming
2. Bisulfite-aware alignment to reference genome
3. Methylation extraction
4. Quality filtering
5. Differential methylation analysis
6. DMR identification
7. Annotation and functional analysis

### 2. Reduced Representation Bisulfite Sequencing (RRBS)
**Description**: Cost-effective method for analyzing methylation in CpG-rich regions.

**Key Tools**:
- Bismark with RRBS mode
- methylKit: RRBS-specific analysis
- RnBeads: Comprehensive methylation analysis

**Input**: RRBS libraries (FASTQ)
**Output**: CpG methylation in enriched regions

### 3. ChIP-seq Analysis
**Description**: Identifies genome-wide binding sites of transcription factors and histone modifications.

**Key Tools**:
- Bowtie2 or BWA: Read alignment
- MACS2/3: Peak calling
- HOMER: Motif discovery and annotation
- DiffBind: Differential binding analysis
- ChIPseeker: Peak annotation
- deepTools: Coverage and heatmap visualization

**Input**: ChIP and input control FASTQ files
**Output**: Peak locations (BED/narrowPeak), differential binding sites, motif enrichment

**Workflow Steps**:
1. Quality control and read trimming
2. Alignment to reference genome
3. Duplicate removal
4. Peak calling (narrow peaks for TFs, broad peaks for histones)
5. Quality metrics (FRiP score, library complexity)
6. Differential binding analysis
7. Motif discovery
8. Gene annotation and functional enrichment

**Common Histone Marks**:
- H3K4me3: Active promoters
- H3K27ac: Active enhancers
- H3K4me1: Poised/active enhancers
- H3K27me3: Polycomb repression
- H3K9me3: Heterochromatin
- H3K36me3: Active gene bodies

### 4. ATAC-seq Analysis
**Description**: Maps chromatin accessibility genome-wide using transposase-accessible chromatin sequencing.

**Key Tools**:
- Bowtie2: Alignment
- MACS2: Peak calling
- ATACseqQC: Quality control
- chromVAR: Chromatin accessibility variation
- HINT: Footprinting analysis

**Input**: ATAC-seq FASTQ files
**Output**: Open chromatin regions, footprints, nucleosome positioning

**Workflow Steps**:
1. Adapter trimming
2. Alignment to reference genome
3. Mitochondrial read removal
4. Duplicate removal
5. Fragment size filtering
6. Peak calling
7. Transcription factor footprinting
8. Differential accessibility analysis

### 5. DNase-seq Analysis
**Description**: Identifies DNase I hypersensitive sites indicating open chromatin regions.

**Key Tools**:
- Bowtie2: Alignment
- Hotspot: Identifying DNase hypersensitive sites
- MACS2: Peak calling
- CENTIPEDE: Footprinting

**Input**: DNase-seq FASTQ files
**Output**: DHSs, footprints

### 6. Hi-C and Chromatin Conformation
**Description**: Analyzes 3D genome organization and chromatin interactions.

**Key Tools**:
- HiC-Pro: Hi-C data processing
- Juicer: Hi-C analysis pipeline
- cooler: Hi-C data storage and analysis
- HiCExplorer: Visualization and analysis
- FitHiC: Significant interaction calling

**Input**: Hi-C FASTQ files (paired-end)
**Output**: Contact matrices, TADs, chromatin loops

**Workflow Steps**:
1. Read alignment and pairing
2. Valid pair filtering
3. Contact matrix generation
4. Normalization (ICE, KR)
5. TAD (Topologically Associating Domain) detection
6. Chromatin loop calling
7. A/B compartment identification

### 7. CUT&RUN / CUT&Tag Analysis
**Description**: Low-input chromatin profiling with reduced background compared to ChIP-seq.

**Key Tools**:
- Bowtie2: Alignment
- SEACR: Sparse Enrichment Analysis for CUT&RUN
- MACS2: Peak calling
- DiffBind: Differential analysis

**Input**: CUT&RUN/CUT&Tag FASTQ files
**Output**: High-resolution binding sites with low background

### 8. Chromatin State Segmentation
**Description**: Integrates multiple histone marks to define chromatin states across the genome.

**Key Tools**:
- ChromHMM: Chromatin state discovery
- Segway: Genome segmentation
- EpiCSeg: Chromatin state calling

**Input**: Multiple ChIP-seq BAM files
**Output**: Genome segmentation into chromatin states (promoters, enhancers, repressed, etc.)

## Data Requirements

- **Sequencing Depth**:
  - WGBS: 10-30X coverage
  - RRBS: 5-10M reads per sample
  - ChIP-seq (TF): 20-40M reads
  - ChIP-seq (Histone): 40-60M reads
  - ATAC-seq: 25-50M reads
  - Hi-C: 300M-1B read pairs
- **Read Length**: 50-150bp (paired-end preferred for Hi-C, ATAC-seq)
- **Biological Replicates**: Minimum 2, preferably 3+

## Best Practices

1. Always include input or IgG controls for ChIP-seq
2. Check fragment size distribution for quality assessment
3. Assess enrichment at known sites
4. Remove duplicate reads appropriately (consider UMIs for low-input)
5. Use appropriate normalization methods
6. Validate findings with orthogonal methods (qPCR, ChIP-qPCR)
7. Consider batch effects in multi-sample studies
8. Report IDR (Irreproducible Discovery Rate) for replicates

## Quality Control Metrics

- **ChIP-seq**: FRiP (Fraction of Reads in Peaks), NSC, RSC, library complexity
- **ATAC-seq**: TSS enrichment, fragment size distribution, library complexity
- **WGBS**: Bisulfite conversion rate (>99%), CpG coverage, duplication rate
- **Hi-C**: Valid pair percentage, cis/trans ratio, distance decay

## Use Cases

- Gene regulation studies
- Cancer epigenomics
- Developmental biology
- Disease epigenetics and biomarkers
- Drug response mechanisms
- Evolution of regulatory elements
- 3D genome organization in disease
- Epigenetic inheritance studies

## Integration with Other Omics

- Correlate DNA methylation with gene expression (RNA-seq)
- Integrate ChIP-seq with transcriptomics for regulatory networks
- Combine ATAC-seq with RNA-seq for enhancer-gene links
- Multi-omics integration for systems biology

## References

- Krueger & Andrews (2011). Bismark: a flexible aligner and methylation caller for Bisulfite-Seq applications. Bioinformatics.
- Zhang et al. (2008). Model-based analysis of ChIP-Seq (MACS). Genome Biology.
- Buenrostro et al. (2013). Transposition of native chromatin for fast and sensitive epigenomic profiling. Nature Methods.
- Lieberman-Aiden et al. (2009). Comprehensive mapping of long-range interactions reveals folding principles of the human genome. Science.
- Ernst & Kellis (2012). ChromHMM: automating chromatin-state discovery and characterization. Nature Methods.
