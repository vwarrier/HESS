# HESS

These contain basic scripts for running HESS and rho HESS. Warning, in progress. 

Please read this for further info: https://huwenboshi.github.io/hess-0.5/

Step 1: Create the files in R
```R


```


Step 2: Run the first script

```bash
    hess.py \
        --bfile ./1kg_eur_1pct/1kg_eur_1pct_chr22 \
        --partition ./ldetect-data/EUR/fourier_ls-chr22.bed \
        --out eq_step1 \
        --chrom 22 \
        --local-hsqg eqforhess.txt
     ```
