# Metabolomics Analysis Pipelines

## Overview

Metabolomics pipelines for analyzing small molecule profiles from mass spectrometry (MS) and nuclear magnetic resonance (NMR) spectroscopy data.

## Available Pipelines

### 1. Untargeted Metabolomics Analysis
**Description**: Comprehensive profiling of all detectable metabolites in a sample without prior knowledge of compounds.

**Key Tools**:
- XCMS: Feature detection and alignment
- MZmine: MS data processing
- MS-DIAL: Data-independent MS/MS deconvolution
- MetaboAnalyst: Statistical analysis and pathway analysis
- CAMERA: Annotation of adducts and isotopes

**Input**: Raw MS data (.mzML, .mzXML, .raw)
**Output**: Feature table, identified metabolites, statistical results

**Workflow Steps**:
1. Raw data conversion and quality control
2. Peak detection and integration
3. Retention time alignment
4. Peak grouping and gap filling
5. Adduct and isotope annotation
6. Metabolite identification (database matching)
7. Statistical analysis and normalization
8. Pathway enrichment analysis

### 2. Targeted Metabolomics Analysis
**Description**: Quantifies specific metabolites of interest using authentic standards and optimized methods.

**Key Tools**:
- Skyline: Small molecule quantification
- TraceFinder: Targeted metabolomics
- MultiQuant: AB SCIEX quantification
- El-MAVEN: LC-MS data analysis

**Input**: LC-MS/MS or GC-MS data, standard curves
**Output**: Absolute metabolite concentrations

**Workflow Steps**:
1. Method development with authentic standards
2. Sample acquisition with internal standards
3. Peak integration and quantification
4. Standard curve generation
5. Concentration calculation
6. Quality control assessment

### 3. Lipidomics Analysis
**Description**: Specialized metabolomics focused on comprehensive lipid profiling across different lipid classes.

**Key Tools**:
- LipidSearch: Lipid identification
- MS-DIAL: Lipidomics workflow
- LipidMatch: Lipid annotation
- LipidomicsAnalyzer: Statistical analysis
- Lipostar: Comprehensive lipidomics platform

**Input**: LC-MS or shotgun MS data
**Output**: Lipid identification, quantification, and classification

**Lipid Classes Covered**:
- Glycerophospholipids (PC, PE, PS, PI, PG)
- Sphingolipids (ceramides, sphingomyelins)
- Glycerolipids (TAG, DAG, MAG)
- Sterols and sterol esters
- Fatty acids and eicosanoids

### 4. NMR Metabolomics Analysis
**Description**: Analyzes metabolite profiles from 1D and 2D NMR spectroscopy data.

**Key Tools**:
- Chenomx NMR Suite: Profiling and quantification
- Bruker TopSpin: NMR data processing
- rNMR: Statistical analysis
- MetaboAnalyst: NMR data analysis module
- HMDB: Human Metabolome Database

**Input**: NMR spectra (FID files)
**Output**: Identified and quantified metabolites

**Workflow Steps**:
1. Spectral preprocessing (phasing, baseline correction)
2. Peak alignment and binning
3. Normalization
4. Metabolite identification
5. Quantification
6. Statistical analysis

### 5. Fluxomics and Isotope Tracing
**Description**: Analyzes metabolic flux using stable isotope labeling (e.g., 13C, 15N).

**Key Tools**:
- INCA: Isotopomer Network Compartmental Analysis
- WUFlux: Stable isotope tracing
- X13CMS: 13C metabolic flux analysis
- IsoCor: Isotope correction

**Input**: Labeled isotope MS data
**Output**: Metabolic flux rates, pathway activity

### 6. Metabolite Identification and Annotation
**Description**: Identifies unknown metabolites using spectral libraries and in silico fragmentation.

**Key Tools**:
- SIRIUS: Molecular formula and structure prediction
- MetFrag: In silico fragmentation
- CSI:FingerID: Compound structure identification
- GNPS: Global Natural Products Social Molecular Networking
- MassBank: MS/MS spectral database

**Input**: MS/MS spectra
**Output**: Putative metabolite identifications with confidence scores

### 7. Pathway and Enrichment Analysis
**Description**: Maps identified metabolites to biological pathways and performs enrichment analysis.

**Key Tools**:
- MetaboAnalyst: Comprehensive pathway analysis
- KEGG: Metabolic pathway database
- MetaCyc: Metabolic pathway collection
- Reactome: Pathway database
- MPEA: Metabolite Pathway Enrichment Analysis

**Input**: List of significantly changed metabolites
**Output**: Enriched pathways, metabolic networks

## Data Requirements

- **MS Platform**: LC-MS, GC-MS, or DI-MS
- **Mass Resolution**: High-resolution preferred (>30,000 FWHM)
- **Polarity**: Positive and negative ionization modes
- **Technical Replicates**: 2-3 per sample
- **Biological Replicates**: Minimum 5-10 per group
- **Quality Control**: Pooled QC samples every 5-10 samples

## Best Practices

1. Include pooled QC samples for quality assessment
2. Randomize sample analysis order
3. Use internal standards for normalization
4. Perform batch correction for large studies
5. Apply appropriate statistical methods (consider non-normal distributions)
6. Validate metabolite identifications with standards when possible
7. Report confidence levels for metabolite identification (MSI levels 1-4)
8. Consider metabolite stability and sample handling

## Sample Preparation Methods

- **Extraction**: Methanol/chloroform extraction, protein precipitation
- **Derivatization**: For GC-MS analysis (BSTFA, MOX)
- **Chromatography**: HILIC, reverse-phase C18, ion exchange
- **Quenching**: For accurate snapshot of metabolome

## Use Cases

- Disease biomarker discovery
- Drug metabolism and pharmacokinetics
- Nutritional studies and food metabolomics
- Plant metabolomics and crop improvement
- Environmental metabolomics
- Systems biology and multi-omics integration
- Personalized medicine
- Toxicology and safety assessment

## Quality Metrics

- Peak shape and chromatographic performance
- Mass accuracy (typically <5 ppm)
- QC sample coefficient of variation (<20-30%)
- Feature detection reproducibility
- Isotope pattern matching

## References

- Smith et al. (2006). XCMS: Processing mass spectrometry data for metabolite profiling. Analytical Chemistry.
- Tsugawa et al. (2015). MS-DIAL: data-independent MS/MS deconvolution for comprehensive metabolome analysis. Nature Methods.
- Pang et al. (2021). MetaboAnalyst 5.0: narrowing the gap between raw spectra and functional insights. Nucleic Acids Research.
- Sud et al. (2007). LMSD: LIPID MAPS structure database. Nucleic Acids Research.
