# Multi-Omics Pipeline Catalog Index

Quick reference guide to all available pipelines in the catalog.

## Genomics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [Variant Calling](genomics/README.md#1-variant-calling-pipeline) | SNV/Indel detection | FASTQ | GATK, FreeBayes | Disease diagnosis, population genetics |
| [Structural Variation](genomics/README.md#2-structural-variation-detection) | Large variants | BAM | Manta, Delly | Cancer genomics, genomic rearrangements |
| [CNV Analysis](genomics/README.md#3-copy-number-variation-cnv-analysis) | Copy number | BAM | CNVkit, Control-FREEC | Cancer genomics, genetic disorders |
| [Genome Assembly](genomics/README.md#4-genome-assembly-pipeline) | De novo assembly | FASTQ | SPAdes, Flye | New genome sequencing |
| [Genome Annotation](genomics/README.md#5-genome-annotation) | Gene prediction | FASTA | MAKER, Augustus | Functional genomics |

## Transcriptomics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [Bulk RNA-seq](transcriptomics/README.md#1-bulk-rna-seq-differential-expression-analysis) | Differential expression | FASTQ | STAR, DESeq2 | Biomarker discovery, disease studies |
| [Single-cell RNA-seq](transcriptomics/README.md#2-single-cell-rna-seq-analysis) | scRNA-seq | FASTQ | Cell Ranger, Seurat | Cell type identification, trajectories |
| [Alternative Splicing](transcriptomics/README.md#3-alternative-splicing-analysis) | Splicing events | BAM | rMATS, SUPPA2 | Isoform analysis, disease mechanisms |
| [lncRNA Analysis](transcriptomics/README.md#4-long-non-coding-rna-lncrna-analysis) | Non-coding RNA | GTF | FEELnc, CPAT | Regulatory RNA discovery |
| [Gene Fusion](transcriptomics/README.md#5-gene-fusion-detection) | Fusion transcripts | FASTQ | STAR-Fusion, Arriba | Cancer diagnostics |
| [Transcript Assembly](transcriptomics/README.md#6-transcript-assembly-and-quantification) | Isoform reconstruction | BAM | StringTie, Cufflinks | Novel transcript discovery |

## Proteomics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [Label-Free Quantification](proteomics/README.md#1-label-free-quantification-lfq) | LFQ | MS raw data | MaxQuant, MSstats | Comparative proteomics |
| [TMT/iTRAQ](proteomics/README.md#2-isobaric-labeling-analysis-tmtitraq) | Multiplex labeling | MS raw data | MaxQuant, Proteome Discoverer | High-throughput quantification |
| [PTM Analysis](proteomics/README.md#3-post-translational-modification-ptm-analysis) | Modifications | MS raw data | MaxQuant, PhosphoSitePlus | Signaling studies, regulation |
| [DIA Analysis](proteomics/README.md#4-data-independent-acquisition-dia-analysis) | DIA/SWATH | DIA data | DIA-NN, Spectronaut | Comprehensive proteome coverage |
| [PPI Analysis](proteomics/README.md#5-protein-protein-interaction-ppi-analysis) | Interactions | AP-MS | SAINT, CompPASS | Protein complex characterization |
| [Targeted Proteomics](proteomics/README.md#6-targeted-proteomics-prmsrm) | PRM/SRM | Targeted MS | Skyline | Biomarker validation |

## Metabolomics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [Untargeted Metabolomics](metabolomics/README.md#1-untargeted-metabolomics-analysis) | Discovery | LC-MS | XCMS, MS-DIAL | Biomarker discovery |
| [Targeted Metabolomics](metabolomics/README.md#2-targeted-metabolomics-analysis) | Quantification | LC-MS/MS | Skyline, TraceFinder | Pathway quantification |
| [Lipidomics](metabolomics/README.md#3-lipidomics-analysis) | Lipid profiling | LC-MS | LipidSearch, MS-DIAL | Lipid metabolism studies |
| [NMR Metabolomics](metabolomics/README.md#4-nmr-metabolomics-analysis) | NMR profiling | NMR spectra | Chenomx, MetaboAnalyst | Non-destructive profiling |
| [Fluxomics](metabolomics/README.md#5-fluxomics-and-isotope-tracing) | Metabolic flux | Labeled MS | INCA, X13CMS | Metabolism studies |
| [Metabolite ID](metabolomics/README.md#6-metabolite-identification-and-annotation) | Annotation | MS/MS | SIRIUS, MetFrag | Unknown identification |
| [Pathway Analysis](metabolomics/README.md#7-pathway-and-enrichment-analysis) | Enrichment | Metabolite lists | MetaboAnalyst, KEGG | Systems-level analysis |

## Epigenomics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [WGBS/BS-seq](epigenomics/README.md#1-dna-methylation-analysis-bs-seqwgbs) | DNA methylation | FASTQ | Bismark, methylKit | Methylation profiling |
| [RRBS](epigenomics/README.md#2-reduced-representation-bisulfite-sequencing-rrbs) | Targeted methylation | FASTQ | Bismark, RnBeads | Cost-effective methylation |
| [ChIP-seq](epigenomics/README.md#3-chip-seq-analysis) | Protein-DNA binding | FASTQ | MACS2, HOMER | Transcription factor binding |
| [ATAC-seq](epigenomics/README.md#4-atac-seq-analysis) | Chromatin accessibility | FASTQ | MACS2, chromVAR | Open chromatin mapping |
| [DNase-seq](epigenomics/README.md#5-dnase-seq-analysis) | DNase hypersensitivity | FASTQ | Hotspot, MACS2 | Regulatory element discovery |
| [Hi-C](epigenomics/README.md#6-hi-c-and-chromatin-conformation) | 3D genome | FASTQ | HiC-Pro, Juicer | Chromatin organization |
| [CUT&RUN/CUT&Tag](epigenomics/README.md#7-cutrun--cuttag-analysis) | Low-input ChIP | FASTQ | SEACR, MACS2 | High-resolution binding sites |
| [Chromatin States](epigenomics/README.md#8-chromatin-state-segmentation) | State segmentation | Multiple ChIP | ChromHMM, Segway | Genome annotation |

## Metagenomics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [16S rRNA Amplicon](metagenomics/README.md#1-16s-rrna-amplicon-sequencing-analysis) | Taxonomic profiling | FASTQ | QIIME2, DADA2 | Microbiome composition |
| [Shotgun Metagenomics](metagenomics/README.md#2-shotgun-metagenomics-analysis) | WGS metagenomics | FASTQ | MetaPhlAn, HUMAnN3 | Comprehensive profiling |
| [Assembly & Binning](metagenomics/README.md#3-metagenome-assembly-and-binning) | MAG reconstruction | FASTQ | MEGAHIT, MetaBAT2 | Genome recovery |
| [Functional Annotation](metagenomics/README.md#4-functional-annotation-and-pathway-analysis) | Function prediction | Contigs | HUMAnN3, eggNOG | Metabolic potential |
| [Metatranscriptomics](metagenomics/README.md#5-metatranscriptomics-analysis) | Gene expression | RNA FASTQ | HUMAnN3, DIAMOND | Active functions |
| [ARG Detection](metagenomics/README.md#6-antibiotic-resistance-gene-arg-detection) | Resistance genes | FASTQ/contigs | CARD RGI, ARGs-OAP | AMR surveillance |
| [Viromics](metagenomics/README.md#7-viral-metagenomics-viromics) | Viral sequences | Contigs | VirSorter2, CheckV | Viral community analysis |
| [Strain Analysis](metagenomics/README.md#8-strain-level-analysis) | Strain tracking | FASTQ | StrainPhlAn, InStrain | Strain diversity |

## Integrated Multi-Omics Pipelines

| Pipeline | Type | Input | Main Tools | Use Case |
|----------|------|-------|-----------|----------|
| [Multi-Omics Integration](integrated_analysis/README.md#1-multi-omics-data-integration) | Data integration | Multiple omics | mixOmics, MOFA+ | Systems biology |
| [Regulatory Networks](integrated_analysis/README.md#2-gene-regulatory-network-inference) | Network inference | Expression + ChIP | SCENIC, ARACNe | Gene regulation |
| [Pathway Enrichment](integrated_analysis/README.md#3-pathway-and-network-enrichment-analysis) | Enrichment | Feature lists | Reactome, Metascape | Pathway analysis |
| [Multi-omics QTL](integrated_analysis/README.md#4-eqtl-and-multi-omics-qtl-analysis) | QTL mapping | Genotype + phenotype | MatrixEQTL, tensorQTL | Genetic regulation |
| [Cancer Multi-Omics](integrated_analysis/README.md#5-cancer-multi-omics-analysis) | Cancer analysis | Tumor multi-omics | TCGA tools, iClusterPlus | Cancer subtypes |
| [Metabolic Modeling](integrated_analysis/README.md#6-metabolic-modeling-and-flux-balance-analysis) | FBA | Network + omics | COBRApy, RAVEN | Metabolism prediction |
| [Time-Series Analysis](integrated_analysis/README.md#7-time-series-multi-omics-analysis) | Temporal dynamics | Time-course data | TimeOmics, ImpulseDE2 | Dynamic processes |
| [Single-Cell Multi-Omics](integrated_analysis/README.md#8-single-cell-multi-omics-integration) | scMulti-omics | sc matrices | Seurat, MOFA+ | Cell state integration |
| [Clinical Integration](integrated_analysis/README.md#9-clinical-multi-omics-and-biomarker-discovery) | Biomarker discovery | Omics + clinical | mixOmics, RandomForest | Precision medicine |
| [Host-Microbe](integrated_analysis/README.md#10-microbial-host-multi-omics) | Host-microbe | Host + microbiome | MaAsLin2, mmvec | Microbiome interactions |

## Quick Navigation by Research Area

### Disease Research
- Genomics: Variant Calling, CNV Analysis
- Transcriptomics: Bulk RNA-seq, Gene Fusion
- Proteomics: Label-Free Quantification, PTM Analysis
- Metabolomics: Untargeted Metabolomics
- Epigenomics: ChIP-seq, DNA Methylation
- Integration: Cancer Multi-Omics, Clinical Integration

### Cancer Biology
- Genomics: Structural Variation, CNV Analysis
- Transcriptomics: Gene Fusion, Alternative Splicing
- Integration: Cancer Multi-Omics

### Microbiome Studies
- Metagenomics: 16S rRNA, Shotgun Metagenomics
- Integration: Host-Microbe Multi-Omics

### Drug Discovery
- Proteomics: Targeted Proteomics, PPI Analysis
- Metabolomics: Targeted Metabolomics, Fluxomics
- Integration: Multi-Omics Integration, Pathway Enrichment

### Systems Biology
- Integration: All integrated analysis pipelines
- All omics types for comprehensive systems-level analysis

---

**Note**: Click on any pipeline name to navigate to detailed documentation including workflows, tools, best practices, and use cases.
