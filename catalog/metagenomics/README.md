# Metagenomics Analysis Pipelines

## Overview

Metagenomics pipelines for analyzing microbial communities from environmental samples, including taxonomic profiling, functional annotation, and microbiome analysis.

## Available Pipelines

### 1. 16S rRNA Amplicon Sequencing Analysis
**Description**: Characterizes bacterial and archaeal communities using 16S rRNA gene sequencing.

**Key Tools**:
- QIIME2: Comprehensive microbiome analysis platform
- DADA2: High-resolution sample inference
- mothur: Microbial ecology analysis
- phyloseq: Microbiome data analysis in R
- PICRUSt2: Functional prediction from 16S data

**Input**: 16S rRNA amplicon FASTQ files (paired-end)
**Output**: OTU/ASV tables, taxonomic composition, diversity metrics, differential abundance

**Workflow Steps**:
1. Quality filtering and denoising
2. ASV/OTU picking (DADA2 or clustering)
3. Chimera removal
4. Taxonomic classification (SILVA, Greengenes, RDP)
5. Phylogenetic tree construction
6. Alpha diversity analysis
7. Beta diversity analysis
8. Differential abundance testing
9. Functional prediction

**Variable Regions**: V1-V9 (most common: V3-V4, V4)

### 2. Shotgun Metagenomics Analysis
**Description**: Whole-genome shotgun sequencing of microbial communities for comprehensive taxonomic and functional profiling.

**Key Tools**:
- MetaPhlAn: Taxonomic profiling
- Kraken2/Bracken: Fast taxonomic classification
- HUMAnN3: Functional profiling
- MEGAHIT: Metagenomic assembly
- MetaBAT2: Binning
- CheckM: Genome completeness assessment

**Input**: Shotgun metagenomic FASTQ files
**Output**: Taxonomic profiles, gene catalogs, functional pathways, MAGs (Metagenome-Assembled Genomes)

**Workflow Steps**:
1. Quality control and host DNA removal
2. Taxonomic profiling
3. Functional profiling
4. De novo assembly (optional)
5. Gene prediction
6. Binning and MAG reconstruction
7. MAG quality assessment and annotation
8. Comparative analysis

### 3. Metagenome Assembly and Binning
**Description**: Reconstructs individual genomes (MAGs) from metagenomic samples.

**Key Tools**:
- MEGAHIT or metaSPAdes: Assembly
- MetaBAT2, MaxBin2, CONCOCT: Binning
- DAS Tool: Bin aggregation
- CheckM or CheckM2: Quality assessment
- GTDB-Tk: Taxonomic classification of MAGs
- dRep: Genome dereplication

**Input**: Quality-filtered metagenomic reads
**Output**: Metagenome-Assembled Genomes (MAGs)

**Quality Criteria**:
- High quality: >90% completeness, <5% contamination
- Medium quality: ≥50% completeness, <10% contamination
- Low quality: <50% completeness, <10% contamination

### 4. Functional Annotation and Pathway Analysis
**Description**: Annotates genes and pathways in metagenomic data.

**Key Tools**:
- HUMAnN3: Metabolic pathway profiling
- eggNOG-mapper: Functional annotation
- KEGG, MetaCyc, COG: Pathway databases
- antiSMASH: Secondary metabolite clusters
- dbCAN: Carbohydrate-active enzymes

**Input**: Assembled contigs or predicted genes
**Output**: Gene functions, pathway abundances, enzyme profiles

### 5. Metatranscriptomics Analysis
**Description**: Analyzes gene expression in microbial communities using RNA sequencing.

**Key Tools**:
- SortMeRNA: rRNA removal
- DIAMOND: Fast sequence alignment
- HUMAnN3: Community-wide gene expression
- Anvi'o: Interactive analysis platform

**Input**: Metatranscriptomic FASTQ files
**Output**: Gene expression profiles, active pathways

**Workflow Steps**:
1. Quality control
2. rRNA removal
3. Host genome filtering
4. Read mapping to gene catalog or reference genomes
5. Gene expression quantification
6. Functional annotation
7. Differential expression analysis

### 6. Antibiotic Resistance Gene (ARG) Detection
**Description**: Identifies and quantifies antibiotic resistance genes in metagenomic samples.

**Key Tools**:
- CARD RGI: Comprehensive Antibiotic Resistance Database
- ARGs-OAP: ARG detection pipeline
- DeepARG: Deep learning-based ARG prediction
- Resfinder: Resistance gene identification

**Input**: Metagenomic contigs or reads
**Output**: ARG catalog, resistance mechanisms, risk assessment

### 7. Viral Metagenomics (Viromics)
**Description**: Identifies and characterizes viral sequences in metagenomic samples.

**Key Tools**:
- VirSorter2: Viral sequence identification
- VIBRANT: Virus identification
- CheckV: Viral genome quality
- vConTACT2: Viral taxonomy
- PhageTerm: Phage termini determination

**Input**: Metagenomic contigs
**Output**: Viral contigs, taxonomy, host prediction

### 8. Strain-Level Analysis
**Description**: Resolves strain-level variation within microbial species.

**Key Tools**:
- StrainPhlAn: Strain-level profiling
- InStrain: Strain tracking
- MIDAS: Metagenomic Intra-Species Diversity Analysis System
- Sigma: Strain-level inference

**Input**: Shotgun metagenomic reads
**Output**: Strain profiles, SNV patterns, strain sharing

## Data Requirements

- **16S rRNA Sequencing**:
  - 20,000-50,000 reads per sample
  - Paired-end 250-300bp
  - 10-20 samples per group minimum

- **Shotgun Metagenomics**:
  - 5-10 GB per sample (complexity-dependent)
  - Paired-end 150bp
  - 50M-200M read pairs per sample

- **Sequencing Depth**: Depends on community complexity and research question

## Best Practices

1. Include negative controls (extraction and PCR blanks)
2. Standardize sample collection and DNA extraction methods
3. Sequence to adequate depth for study goals
4. Use mock communities for validation
5. Remove contaminant sequences (host, reagents)
6. Normalize data appropriately for compositional nature
7. Consider rarefaction vs. compositional data analysis
8. Validate key findings with qPCR or culture-based methods
9. Report detailed metadata (MIMARKS/MIMS standards)

## Sample Types

- Human microbiome (gut, oral, skin, vaginal)
- Environmental (soil, water, air)
- Marine and freshwater ecosystems
- Food and fermentation
- Agricultural (plant rhizosphere, animal rumen)
- Built environment

## Statistical Analysis

- Alpha diversity: Shannon, Simpson, Chao1, Faith's PD
- Beta diversity: UniFrac, Bray-Curtis, Jaccard
- Differential abundance: DESeq2, ANCOM-BC, LEfSe, ALDEx2
- Machine learning: Random Forest, PCoA, PERMANOVA
- Network analysis: Co-occurrence networks

## Use Cases

- Human health and disease associations
- Environmental monitoring and bioremediation
- Agricultural microbiome optimization
- Food safety and quality
- Antibiotic resistance surveillance
- Probiotic and prebiotic development
- Biogeochemical cycling studies
- Climate change impacts

## Quality Control Metrics

- Read quality scores
- Contamination levels
- Sequencing depth adequacy
- Good's coverage
- Rarefaction curves
- Sample similarity to controls

## Databases and Resources

- **Taxonomic**: SILVA, Greengenes, RDP, GTDB, NCBI RefSeq
- **Functional**: KEGG, MetaCyc, COG, SEED, UniProt
- **Resistance**: CARD, ResFinder, ARG-ANNOT
- **Viral**: NCBI Viral, IMG/VR, RefSeq Viral

## References

- Bolyen et al. (2019). Reproducible, interactive, scalable and extensible microbiome data science using QIIME 2. Nature Biotechnology.
- Callahan et al. (2016). DADA2: High-resolution sample inference from Illumina amplicon data. Nature Methods.
- Beghini et al. (2021). Integrating taxonomic, functional, and strain-level profiling of diverse microbial communities with bioBakery 3. eLife.
- Li et al. (2015). MEGAHIT: an ultra-fast single-node solution for large and complex metagenomics assembly. Bioinformatics.
- Kang et al. (2019). MetaBAT 2: an adaptive binning algorithm for robust and efficient genome reconstruction from metagenome assemblies. PeerJ.
