---
title: Run an R script to analyze difference between with DESID Emissions and the base case (no emission reduction) 
weight: 20
--- 

###  Connect to the NICE DCV 

1. Select Activities, then click on Terminal Image (MATE Terminal)



2. Change directories to the location of the R script 

```csh
cd /shared/pcluster-cmaq/qa_scripts/workshop
```

3. Run the R script 

```
Rscript compare_EQUATES_benchmark_output_CMAS_pcluster_hpc7g.18xlarge.DESID_vs_base.r

```
