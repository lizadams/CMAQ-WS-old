---
title: Review timings for CMAQ on the HPC7g Cluster
weight: 23
---

:::alert{type=info}
links to CMAQ EPA site
:::


1. **Change directories to the run script location**

`cd /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts`


2. **Use tail to review the timing**

`tail -n 20 run_cctm5.4+_Bench_2018_12US1_cb6r5_ae6_20200131_MYR.192.12x16pe.2day.20171222start.3x64.log`


3. **Commpare the timing with the results in the [CMAQ on AWS Tutorial](https://pcluster-cmaq.readthedocs.io/en/latest/user_guide_pcluster/Performance-Opt/performance-optimization.html#benchmark-timing-for-hpc7g-16xlarge-with-64-processors-per-node)**
