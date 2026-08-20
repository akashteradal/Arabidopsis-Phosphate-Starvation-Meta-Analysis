# DESeq2 Differential Expression Analysis

This directory contains the differential expression analysis results generated using DESeq2 for the five RNA-seq datasets included in the comparative transcriptomic meta-analysis.

DESeq2 was used to compare phosphate-starved samples with their corresponding control samples for each dataset.

## Analysis Criteria

Differentially expressed genes were classified using the following thresholds:

- Upregulated genes: log₂FC > +1.5
- Downregulated genes: log₂FC < −1.5
- Statistical significance: padj < 0.05

The resulting DEG lists were used for downstream comparative meta-analysis and functional enrichment analysis.

## Datasets

- Dataset 1 — GSE183312
- Dataset 2 — GSE128250 (1 hour)
- Dataset 3 — GSE128250 (2 hours)
- Dataset 4 — GSE217158
- Dataset 5 — GSE278345

The DESeq2 outputs generated for each dataset are provided in this directory.
