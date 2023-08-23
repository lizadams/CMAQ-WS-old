---
title: Get to know the CMAQ run script
weight: 23
---

:::alert{type=info}
links to CMAQ EPA site
:::


1. **View the top of the run script.**

`cd /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts/`

`head run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.csh`

Output:

```
#!/bin/csh -f

## For Parallel Cluster 64 cores x 3 = 192 
## data on /fsx or lustre data directory
## https://dataverse.unc.edu/dataset.xhtml?persistentId=doi:10.15139/S3/LDTWKH
#SBATCH --nodes=3
#SBATCH --ntasks-per-node=64
#SBATCH --exclusive
#SBATCH -J CMAQ
#SBATCH -o /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts/run_cctm5.4+_Bench_2018_12US1_cb6r5_ae6_20200131_MYR.192.12x16pe.2day.20171222start.3x64.log
```

Note, this section of the run script determines how many compute nodes will be provisioned, and how many cores per node will be used.


2. **View the domain decomposition settings in the run script**

`grep -B 2 NPCOL run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.csh`

Output

```

#> Horizontal domain decomposition
if ( $PROC == serial ) then
   setenv NPCOL_NPROW "1 1"; set NPROCS   = 1 # single processor setting
else
   @ NPCOL  =  12; @ NPROW =  16
   @ NPROCS = $NPCOL * $NPROW
   setenv NPCOL_NPROW "$NPCOL $NPROW"; 

```

Note, that the multiplication of NPCOLxNPROW must equal the SLURM settings (nodes * ntasks-per-node)

Example.

NPCOL x NPROW 
12    x 16    = 192

nodes x ntasks-per-node

3     x  64   = 192

