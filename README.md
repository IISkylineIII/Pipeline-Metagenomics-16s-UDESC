# Pipeline-Metagenomics-16s-UDESC


# 1. Sample Collection and DNA Extraction
* Samples: Fifteen fresh fecal samples were collected in pools on days 1, 7, 21, 35, and 42 using sterile spatulas. Each sample was placed in sterile 1.5 mL microtubes, with a maximum volume of 0.5 mL.
* Storage: After collection, the samples were kept on dry ice and transported to Neoprospecta Microbiome Technologies in Florianópolis, Brazil.
* DNA Extraction: DNA was extracted using the QIAamp DNA Stool Mini Kit (Hilden, Germany). The extracted DNA was eluted in 50 μL of AE buffer.
* Quantification and Purity: DNA concentration and purity were assessed using the NanoDrop ND-1000 spectrophotometer (Thermo Fisher Scientific), with a 260/280 nm absorbance ratio of 1.83 ± 0.04 and a 260/230 nm ratio of 2.09 ± 0.16.

# 2. Sequencing
*  Sequencing Platform: Sequencing was performed on the Illumina MiSeq platform, generating approximately 50,000 reads per sample.
* File Format: The output sequences were in FASTQ format, containing base calls and associated quality scores.

# 3. Sequence Processing
* 3.1 Sequence Quality Assessment
* FastQC: The quality of the FASTQ files was evaluated using FastQC v.0.11.8, checking Phred scores and base-by-base quality. Sequences with Phred scores below 20 were discarded.
* Primer Trimming: Primers were removed from the sequences to ensure accuracy in subsequent analysis.

# 3.2 OTU Clustering
* Mothur: The filtered sequences were clustered into operational taxonomic units (OTUs) at 97% identity using the Mothur v.23.0.rc1 software.

# 3.3 Chimera Removal
* Chimeras: Chimeric sequences were removed to enhance the accuracy of the taxonomic analysis.

# 4. Taxonomic Classification
* Vsearch and SILVA: OTUs were classified using the SILVA database and the Vsearch algorithm for taxonomic assignment of sequences.

# 5. Diversity Analysis
* 5.1 Alpha Diversity
Shannon Index (H): Alpha diversity was calculated using the Shannon index, and a t-test was performed to compare diversity between experimental groups (p < 0.05).

# 5.2 Beta Diversity
* Bray-Curtis and PCoA: Beta diversity was calculated using Bray-Curtis dissimilarity and visualized through Principal Coordinates Analysis (PCoA).

# 6. Differential Abundance
* Tools Used: Differential abundance was analyzed using the DESeq2, EdgeR, and metagenomeSeq packages to identify changes in relative abundance of OTUs across treatments.

# 7. Visualization and Statistical Analysis
* Data Visualization: Results were integrated into R (v.4.3.1) using the Phyloseq package, allowing visualization of various alpha and beta diversity metrics.
* PERMANOVA: OTU comparisons between treatments and controls were conducted using the PERMANOVA test, utilizing the vegan package.
