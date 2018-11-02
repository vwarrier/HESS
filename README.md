# HESS

These contain basic scripts for running HESS and rho HESS. Warning, in progress. 

Please read this for further info: https://huwenboshi.github.io/hess-0.5/

Step 1: Create the files in R

HESS requires a single file in plain text or gzipped text containing the following columns to be present in the GWAS summary association data:

SNP - rs ID of the SNP (e.g. rs62442).
CHR - Chromosome number of the SNP. This should be a number between 1 and 22.
BP - Base pair position of the SNP.
A1 - Effect allele of the SNP. The sign of the Z-score is with respect to this allele.
A2 - The other allele of the SNP.
Z - The Z-score of the SNP.
N - Sample size of the SNP.

```R
library(data.table)


```


Step 2: Run the first script

```bash

for i in {1..22}; do python2 hess.py \
        --bfile ./1kg_eur_1pct/1kg_eur_1pct_chr${i} \
        --partition ./ldetect-data/EUR/fourier_ls-chr${i}.bed \
        --out Family_step1 \
        --chrom ${i} \
        --local-hsqg FamilyforHESS.txt; done
        
 python2  hess.py \
        --prefix Family_step1 \
        --out step2_Family
        
  ### For GWAS with N < 50K
        
 python2  hess.py \
        --prefix SQ_step1 \
        --tot-hsqg 0.12 0.012 \
        --out step2_SQ        
        
     ```
