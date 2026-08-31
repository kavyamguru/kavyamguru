# Kavya Manjula Gurubasavaiah

**Single-cell and perturbation bioinformatics · machine learning**
MSc Bioinformatics, University of Edinburgh · Edinburgh, UK

CRISPRi perturbation screens, cell foundation models, and out-of-core pipelines for
single-cell data that will not fit in memory. Two years at the bench before moving to
computation, so I know how the data was made — and I measure a dataset before I model it.

📄 **[Portfolio](https://kavyamguru.github.io)** · [LinkedIn](https://www.linkedin.com/in/kavyamg) · mgkavya6@gmail.com

---

## Selected work

### [Arc Virtual Cell Challenge 2026](https://github.com/kavyamguru/vcc_2026)
Predicting how three anonymised human cell lines respond to 300 CRISPRi gene knockdowns
from their unperturbed profiles alone — zero-shot generalisation under distribution shift.
360,000 cells × 18,533 genes.

- Measured the **noise floor (0.0132 MAE)** from non-targeting guides and the **ceiling (~0.30)**
  by scoring control cells against each other, before building anything.
- Identified all three anonymised cell contexts from marker genes alone, and caught
  undocumented subsampling in the released data (400 cells per guide, SD 0.0).
- Diagnosed a metric pinned at its floor: truncation alone cost `nmae` −6. Predicting at full
  density moved the score from **−0.9976 to −0.0317** and the rank from 455 to 274.
- Fine-tuned **STATE** (242M-parameter perturbation transformer, ESM2 embeddings) and built the
  count-conversion and submission path end to end.
- Found the released training config excluded `competition_train` — **221,273 cells**, three
  quarters of the available in-distribution data.

### [gse2034-relapse-prediction](https://github.com/kavyamguru/gse2034-relapse-prediction)
Breast cancer relapse classification on GEO GSE2034 (286 tumours, 22,215 probes), with scaling
and feature selection refit inside every cross-validation fold. A controlled experiment measures
how much the common shortcut inflates reported performance: **+0.120 ROC-AUC** — enough to change
which model looks best. Reports the honest 0.61–0.64 test AUC rather than the flattering one.

### [elaniti-nextflow-metagenomics](https://github.com/kavyamguru/elaniti-nextflow-metagenomics)
Modular Nextflow DSL2 pipeline with imported process modules, samplesheet-driven channels,
Docker, and a Slurm profile. Proof-of-concept scope, built to demonstrate pipeline structure
and portability across local, container and cluster execution.

### [MSc_Dissertation_Kvass](https://github.com/kavyamguru/MSc_Dissertation_Kvass)
Integrated 16S + shotgun metagenomics of kvass fermentation. **Four taxonomic profilers run in
parallel and compared for agreement** rather than trusting one, plus functional profiling via
HUMAnN3 and DRAM2. Versioned manifests and reproducible outputs throughout.

### [LabHelpr](https://www.labhelpr.com/) · [source](https://github.com/kavyamguru/labhelpr-app)
Deployed web platform for wet-lab scientists: 13 experimental calculators, a statistics module
that checks its own assumptions, and an offline-capable electronic lab notebook.

---

## Technical stack

**Single cell & perturbation** — AnnData/h5ad · CSR sparse · out-of-core HDF5 with h5py ·
CRISPRi Perturb-seq · differential expression (Wilcoxon, Benjamini–Hochberg) · marker-gene
annotation · cell-eval

**Machine learning** — scikit-learn · Random Forest, SVM, logistic regression, XGBoost ·
leakage-safe cross-validation with Pipelines · ROC-AUC, PR-AUC · arc-state (STATE) fine-tuning
and zero-shot inference · ESM2 embeddings

**Statistics** — multiple-testing correction and FDR · nonparametric tests · linear models and
ANOVA · GLMs with Poisson and binomial outcomes

**Transcriptomics** — RNA-seq end to end · FastQC/MultiQC · STAR, HISAT2 · DESeq2, edgeR ·
TPM/TMM/VST normalisation · PCA · GO and KEGG enrichment

**Engineering** — Python · R · Bash · numpy, pandas, scipy.sparse · Nextflow DSL2 · Docker ·
Slurm/HPC · Git · Linux · RMarkdown

**Wet lab** — DNA/RNA extraction · PCR and qPCR · cloning · protein expression · western
blotting · cell culture

**In progress** — Scanpy, Seurat and Cell Ranger · AWS (S3, Batch, IAM) · PyTorch from first
principles · scVI

---

## Currently

Competing in the **Arc Virtual Cell Challenge 2026** (submission deadline 5 November).
Bioinformatics and AI-evaluation contract work — designing deterministic computational biology
tasks and assessing model outputs for factual accuracy and reproducibility.
