# Comparative Transcriptomics Meta-Analysis of Early and Late Phosphate Starvation Responses in *Arabidopsis thaliana*

A comparative transcriptomic meta-analysis of publicly available RNA-seq datasets to investigate conserved molecular responses to early and late phosphate starvation in *Arabidopsis thaliana*.

---

## Project Overview

Phosphate is an essential macronutrient required for plant growth, development, energy metabolism, nucleic acid biosynthesis, membrane formation, and several cellular processes.

Under phosphate deficiency, plants activate a coordinated phosphate starvation response involving changes in phosphate uptake, internal phosphate recycling, membrane lipid remodeling, root adaptation, and metabolic reprogramming.

Although several RNA-seq studies have investigated phosphate starvation in *Arabidopsis thaliana*, individual studies often focus on specific tissues, developmental stages, or stress durations. Differences between experimental conditions and datasets can make direct comparison difficult.

This project used a comparative transcriptomic meta-analysis of five independent paired-end RNA-seq datasets. A standardized bioinformatics workflow was applied to identify conserved molecular responses associated with acute and chronic phosphate starvation.

The study also investigated **AT1G08440** as a candidate gene associated with long-term phosphate starvation and proposed a hypothesis regarding its potential role in malate-mediated rhizosphere phosphate mobilization.

---

## Objectives

### Primary Objective

To perform a comparative transcriptomic meta-analysis to identify conserved molecular responses to short-term and long-term phosphate starvation in *Arabidopsis thaliana*.

### Secondary Objectives

- To identify conserved differentially expressed genes (DEGs) under short-term and long-term phosphate starvation.
- To compare transcriptomic responses between short-term and long-term phosphate starvation.
- To evaluate the potential role of the candidate gene **AT1G08440** in long-term phosphate starvation.
- To characterize the biological processes associated with acute and chronic phosphate starvation.
- To develop a temporal interpretation of phosphate starvation responses.

---

# Study Design

Five independent publicly available paired-end RNA-seq datasets were analyzed.

A total of 30 paired-end libraries were analyzed, with three control and three phosphate-starved biological replicates represented for each dataset.

The datasets represented acute phosphate starvation at 1–2 hours and chronic phosphate starvation at 8–21 days.

| Dataset | GEO Accession | Tissue | Duration | Response |
|---|---|---|---|---|
| 1 | GSE183312 | Whole seedling | 21 days | Chronic |
| 2 | GSE128250 (A) | Root apex | 1 hour | Acute |
| 3 | GSE128250 (B) | Root apex | 2 hours | Acute |
| 4 | GSE217158 | Isolated root | 8 days | Chronic |
| 5 | GSE278345 | Whole seedling | 8 days | Chronic |

The datasets were processed using a standardized bioinformatics workflow to reduce computational variability between studies.


## Computational Environment

The RNA-seq data processing and downstream bioinformatics analysis were performed in a Linux-based computational environment.

- **Operating System:** Ubuntu Linux / WSL2
- **Programming Language:** R
- **Statistical Analysis:** DESeq2
- **Reference Genome:** *Arabidopsis thaliana* TAIR10
- **Package/Environment Management:** Conda
- **Quality Control:** FastQC and MultiQC
- **Read Trimming:** Trimmomatic
- **Genome Alignment:** STAR
- **Gene Quantification:** featureCounts
- **Meta-analysis:** InteractiVenn
- **Functional Enrichment:** ShinyGO
---


## Bioinformatics Workflow

**FASTQ Files**  
Raw paired-end RNA-seq reads  
↓  
**Quality Control** — FastQC & MultiQC  
↓  
**Read Trimming** — Trimmomatic  
↓  
**Post-trimming Quality Check** — FastQC  
↓  
**Reference Genome & Annotation** — TAIR10 FASTA + GTF  
↓  
**STAR Genome Index**  
↓  
**STAR Alignment**  
↓  
**Sorted BAM Files**  
↓  
**Gene Quantification** — featureCounts  
↓  
**Count Matrix** — Gene × Sample count matrix  
↓  
**Differential Expression Analysis** — DESeq2  
↓  
**Differentially Expressed Genes** — Upregulated: log₂FC > +1.5; Downregulated: log₂FC < −1.5; padj < 0.05 
↓  
**Meta-analysis** — InteractiVenn  
↓  
**Short-term Intersection** — 1–2 h  
**Long-term Intersection** — 8–21 d  
↓  
**GO Biological Process Enrichment** — ShinyGO (FDR < 0.05)


## Results and Analysis

### 1. Acute Phosphate Starvation Response

The short-term phosphate starvation datasets represented responses observed after 1–2 hours of phosphate deficiency.

The meta-analysis identified conserved transcriptional responses associated with rapid phosphate-deficiency signalling, stress adaptation, metabolic adjustment, and early changes in root growth.

Phosphate-responsive transport and signalling genes, including members of the PHT1 family, showed early responses to phosphate limitation. Metabolic adjustment was also observed through genes associated with carbon and energy metabolism, including PEPC1 and PPCK1.

Stress-responsive genes such as LEA14, LTI78/RD29A, GolS3, and RAS1 were also associated with the acute response. Changes involving XTH31 and ACS2 suggested early modification of root growth and development under phosphate limitation.

Overall, the acute response represents a rapid transcriptional adjustment that helps the plant respond to the immediate effects of phosphate deficiency.

### 2. Chronic Phosphate Starvation Response

The long-term datasets represented phosphate starvation responses observed over 8–21 days.

The chronic response showed broader transcriptional adaptation associated with phosphate acquisition, internal phosphate recycling, nutrient homeostasis, membrane lipid remodeling, and metabolic adjustment.

Several purple acid phosphatase genes, including PAP12, PAP14, PAP17, and PAP25, were associated with the long-term response, supporting their role in phosphate mobilization and recycling.

Genes associated with nutrient transport and homeostasis, including NRT1.5, UMAMIT17, and UMAMIT20, also showed changes during prolonged phosphate starvation.

The long-term response further involved genes associated with shoot–root communication and phosphate homeostasis, including NAC003, NF-YA10, SWEET13, and PHT1;8.

Genes such as RNS1, SQD1, SQD2, and MGD2 were associated with internal phosphate recycling and membrane lipid adaptation during prolonged phosphate deficiency.

### 3. Temporal Comparison of Phosphate Starvation Responses

Comparison of the short-term and long-term meta-analysis results revealed a temporal shift in the transcriptional response to phosphate starvation.

The acute response was primarily associated with rapid stress signalling, metabolic adjustment, and early adaptation to phosphate deficiency.

In contrast, the chronic response involved sustained nutrient acquisition, phosphate recycling, nutrient homeostasis, membrane remodeling, and long-term metabolic adaptation.

This temporal pattern suggests that *Arabidopsis thaliana* progressively changes its molecular response from an immediate stress-response state to a more coordinated nutrient-acquisition and recycling strategy during prolonged phosphate starvation.

### 4. Functional Enrichment Analysis

Gene Ontology Biological Process enrichment analysis was performed using ShinyGO.

The enrichment analysis supported the functional differences observed between acute and chronic phosphate starvation responses.

The acute response was associated mainly with biological processes related to stress response, detoxification, hormonal signalling, and metabolic adjustment.

The chronic response showed stronger association with nutrient adaptation, phosphate transport and homeostasis, phosphate recycling, and interactions between phosphate and other nutrient pathways.

The functional enrichment analysis therefore supported the temporal interpretation of phosphate starvation responses obtained from the transcriptomic meta-analysis.


## 5. Integrated Biological Interpretation

The conserved genes identified from the short-term and long-term meta-analyses were integrated with their associated biological functions to develop a temporal model of the Arabidopsis phosphate-starvation response.

### Short-term Response

The short-term response represents the early transcriptional adjustment to phosphate deficiency. Conserved genes were associated with phosphate uptake, metabolic adjustment, stress adaptation, and root growth regulation.

Key genes identified in the short-term analysis included members of the PHT1 family, PEPC1, PPCK1, LEA14, LTI78/RD29A, GolS3, RAS1, XTH31, and ACS2.

### Long-term Response

The long-term response represents sustained adaptation to prolonged phosphate deficiency. Conserved genes were associated with root adaptation, shoot–root communication, internal phosphate recycling, membrane lipid remodeling, and phosphate acquisition.

Key genes included PAP12, PAP14, PAP17, PAP25, NRT1.5, UMAMIT17, UMAMIT20, NAC003, NF-YA10, SWEET13, PHT1;8, RNS1, SQD1, SQD2, MGD2, and the candidate gene AT1G08440.

### Integrated Response Model

The integrated model summarizes the temporal transition from early stress signalling and metabolic adjustment during short-term phosphate starvation to sustained phosphate acquisition, internal phosphate recycling, nutrient homeostasis, and metabolic adaptation during long-term phosphate starvation.

[View Integrated Biological Interpretation Results](results/Biological-Interpretation/)

> **Note:** NAS3 is a known phosphate-starvation-responsive gene. The proposed involvement of AT1G08440 in malate-mediated rhizosphere phosphate mobilization is a hypothesis generated from the transcriptomic meta-analysis and has not been experimentally validated.


### 6. Overall Interpretation

The comparative meta-analysis demonstrates that phosphate starvation produces distinct temporal transcriptional responses in *Arabidopsis thaliana*.

Acute phosphate deficiency triggers rapid stress signalling and metabolic adjustment, whereas chronic phosphate deficiency promotes sustained nutrient acquisition, phosphate recycling, homeostasis, and metabolic adaptation.

The integration of independent RNA-seq datasets provides a broader view of conserved phosphate-starvation responses and highlights candidate genes, including AT1G08440, for further functional investigation.


## Key Findings

- Acute (1–2 h) and chronic (8–21 d) phosphate starvation produced distinct transcriptional responses in *Arabidopsis thaliana*.
- Acute phosphate starvation was associated with rapid stress signalling, phosphate uptake, energy conservation, and metabolic adjustment.
- Chronic phosphate starvation was associated with phosphate recycling, nutrient homeostasis, membrane lipid remodeling, and metabolic adaptation.
- Comparative analysis identified conserved transcriptional responses across independent RNA-seq datasets.
- Functional enrichment revealed a temporal shift from early stress responses toward sustained adaptation during prolonged phosphate deficiency.
- **AT1G08440** was identified as a candidate gene associated with the long-term phosphate-starvation response.
- AT1G08440 was proposed as a hypothesis candidate for potential involvement in malate-mediated rhizosphere phosphate mobilization.
- The proposed role of AT1G08440 requires experimental validation.


## Hypothesis and Candidate Gene

### AT1G08440

AT1G08440 was consistently upregulated across the long-term (8–21 days) phosphate starvation datasets and was selected as a candidate gene for further investigation.

AT1G08440 encodes a putative ALMT family protein with limited functional characterization.

### Proposed Hypothesis

We hypothesize that **AT1G08440 may contribute to malate-mediated rhizosphere phosphate mobilization, thereby enhancing phosphate acquisition during prolonged phosphate starvation.**

This is a **hypothesis generated from the transcriptomic meta-analysis** and is not an experimentally validated function of AT1G08440.

### Proposed Validation

The proposed role of AT1G08440 requires experimental validation through:

- qRT-PCR
- CRISPR-Cas9 functional studies
- Root malate exudation assays
- Phosphate uptake assays


## Conclusion

Comparative transcriptomic meta-analysis revealed distinct molecular responses to acute (1–2 h) and chronic (8–21 d) phosphate starvation in *Arabidopsis thaliana*.

Acute phosphate starvation activated stress signalling, phosphate uptake, and energy conservation, whereas chronic phosphate starvation promoted phosphate recycling, lipid remodeling, and metabolic adaptation.

Functional enrichment analysis revealed a temporal shift from early stress responses to sustained adaptation under prolonged phosphate deficiency.

AT1G08440 was identified as a candidate gene for long-term phosphate starvation adaptation and may contribute to malate-mediated rhizosphere phosphate mobilization.

Overall, this study provides insights into the temporal molecular mechanisms of phosphate starvation and identifies a potential candidate for further investigation of phosphorus-use efficiency in plants.


## Repository Structure

The repository is organized to document the major components of the transcriptomic meta-analysis.

- `README.md` — Project overview, objectives, study design, computational environment, workflow, results, hypothesis, and conclusion.
- `24L10904(Akash Teradal)- final report.pdf` — Final MSc Bioinformatics dissertation report.
- `results/` — Analysis results and output files.
  - `DESeq2/` — Differential expression results.
  - `PCA/` — Principal Component Analysis plots.
  - `Volcano/` — Volcano plots.
  - `Meta-analysis/` — InteractiVenn and conserved DEG intersection results.
  - `ShinyGO/` — Gene Ontology Biological Process enrichment results.
The transcriptomic datasets used in this study were obtained from publicly available resources and were processed for downstream analysis.


## Data Availability

The RNA-seq datasets used in this study were obtained from the **NCBI Gene Expression Omnibus (GEO)** database.

Five independent RNA-seq datasets were analyzed from four GEO accessions:

- GSE183312
- GSE128250 (1 hour and 2 hours)
- GSE217158
- GSE278345

The datasets represented different phosphate-starvation durations and tissues and were processed using the standardized bioinformatics workflow described in this repository.

Detailed information about the datasets and their experimental conditions is provided in the final dissertation report.

## References

1. Rubio, V., Linhares, F., Solano, R., Martín, A. C., Iglesias, J., Leyva, A., & Paz-Ares, J. (2001). An MYB transcription factor regulates the coordinated response of Arabidopsis to phosphate starvation. *Genes & Development*, 15(16), 2122–2133.

2. Bustos, R., Castrillo, G., Linhares, F., et al. (2010). A central regulatory system largely controls transcriptional activation and repression responses to phosphate starvation in Arabidopsis. *PLoS Genetics*, 6(9), e1001102.

3. Puga, M. I., Mateos, I., Charukesi, R., et al. (2014). SPX1 is a phosphate-dependent inhibitor of PHOSPHATE STARVATION RESPONSE 1 in Arabidopsis. *Proceedings of the National Academy of Sciences*, 111(41), 14947–14952.

4. Woo, J., MacPherson, C. R., Liu, J., et al. (2012). The response and recovery of the Arabidopsis thaliana transcriptome to phosphate starvation. *BMC Plant Biology*, 12, 62.

5. Secco, D., Wang, C., Arpat, B. A., et al. (2017). RNA-seq analysis identifies an intricate regulatory network controlling plant phosphate starvation responses. *Frontiers in Plant Science*, 8, 1065.

6. Hoekenga, O. A., Maron, L. G., Piñeros, M. A., et al. (2006). AtALMT1, which encodes a malate transporter, is identified as one of several genes critical for aluminum tolerance in Arabidopsis. *Proceedings of the National Academy of Sciences*, 103(25), 9738–9743.


## Contact

**Akash Teradal**

- Email: akashteradal005@gmail.com
- LinkedIn: [(https://www.linkedin.com/in/your-profile/)](https://www.linkedin.com/in/akash-teradal-68776535a)
