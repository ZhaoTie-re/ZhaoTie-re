```nextflow
#!/usr/bin/env nextflow
/*
 * Zhao Tie
 * PhD student, Graduate School of Medicine, Kyoto University
 * WGS data processing and statistical genetics
 */

workflow {
    CALL(crams)                                      // gVCF calling, joint genotyping
    PARETOGT(CALL.out, array_calls)                  // genotype QC thresholds
    ANNOTATE(PARETOGT.out)                           // snpEff, ANNOVAR
    HLA_TYPING(crams)                                // HLA-HD on extracted reads
    POPGMM(pca_scores, reference_panel)              // ancestry-matched cohorts
    ASSOC(ANNOTATE.out, HLA_TYPING.out, POPGMM.out)  // GWAS, gene tests, HLA
    DISEASELENS(params.disease)                      // what is already known
}

workflow PROTEOMICS {
    SOMA_QC(adat_files)                              // SomaScan QC
}
```

<pre>
$ ls ~/src
<a href="https://github.com/ZhaoTie-re/ParetoGT">ParetoGT</a>/        genotype QC: DP, GQ, AF cutoffs at the knee of concordance vs miss rate
<a href="https://github.com/ZhaoTie-re/PopGMM">PopGMM</a>/          GMM in reference PCA space: posterior ancestry, nested matched cohorts
<a href="https://github.com/ZhaoTie-re/DiseaseLens">DiseaseLens</a>/     dated snapshots of a disease's genetics and related conditions
<a href="https://github.com/ZhaoTie-re/cteph_agp3k.v6">cteph_agp3k.v6</a>/  WGS case-control study: calling checks, QC, HLA, GWAS, gene tests
<a href="https://github.com/ZhaoTie-re/soma_qc">soma_qc</a>/         SomaScan proteomics QC

$ cat ~/.stack
nextflow  python  R  gatk  samtools  bcftools  plink2  saige  rvtests  hla-hd  slurm

$ git config user.email
tie.zhao@csml.org
</pre>
