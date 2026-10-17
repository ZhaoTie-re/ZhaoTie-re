### Zhao Tie

Statistical genetics on whole-genome sequencing data.\
PhD student, Graduate School of Medicine, Kyoto University.

```nextflow
workflow {
    PARETOGT(wgs_calls, array_calls)            // genotype QC thresholds
    POPGMM(pca_scores, reference_panel)         // ancestry-matched cohorts
    ASSOC(wgs_calls, PARETOGT.out, POPGMM.out)  // common, rare, HLA
    DISEASELENS(params.disease)                 // what is already known
}
```

[ParetoGT](https://github.com/ZhaoTie-re/ParetoGT) sets DP, GQ and allele-fraction cutoffs for WGS genotypes at the knee of the Pareto front of concordance against miss rate, with array genotypes as truth.

[PopGMM](https://github.com/ZhaoTie-re/PopGMM) fits a Gaussian mixture in the PCA space of a reference panel, gives every sample a posterior ancestry, and cuts nested, ancestry-matched case–control sets.

[DiseaseLens](https://github.com/ZhaoTie-re/DiseaseLens) keeps dated snapshots of what is known about a disease's genetics and related conditions, from Open Targets, PubMed and Europe PMC.

[cteph_agp3k.v6](https://github.com/ZhaoTie-re/cteph_agp3k.v6) is the WGS case–control study they were built for. [soma_qc](https://github.com/ZhaoTie-re/soma_qc) is QC for SomaScan proteomics.

Nextflow, Python, R, PLINK 2, SAIGE, REGENIE, SLURM\
zxjs90408@gmail.com
