## Zhao Tie

PhD student, Graduate School of Medicine, Kyoto University.

I work on statistical genetics with whole-genome sequencing data, from genotype calls to association results. I write the analyses as reproducible pipelines for HPC clusters.

### Software

| Step | Repository | What it does |
|---|---|---|
| Genotype QC | [ParetoGT](https://github.com/ZhaoTie-re/ParetoGT) | Chooses WGS genotype QC thresholds that balance accuracy against data loss, calibrated against array genotypes. |
| Ancestry | [PopGMM](https://github.com/ZhaoTie-re/PopGMM) | Probabilistic ancestry with PCA and Gaussian mixture models, and ancestry-matched case–control cohorts. |
| Evidence review | [DiseaseLens](https://github.com/ZhaoTie-re/DiseaseLens) | Dated, traceable knowledge graphs of a disease's genetics and related conditions. |

### Analyses

- [cteph_agp3k.v6](https://github.com/ZhaoTie-re/cteph_agp3k.v6): a whole-genome sequencing case–control study. It covers quality control, principal components, common-variant GWAS, rare-variant gene tests and HLA association.
- [soma_qc](https://github.com/ZhaoTie-re/soma_qc): quality control of SomaScan proteomics data.

**Tools:** Nextflow, Python, R, PLINK 2, SAIGE, REGENIE, SLURM.

**Contact:** zxjs90408@gmail.com
