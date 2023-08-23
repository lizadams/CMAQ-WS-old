---
title: Install VERDI on HPC cluster
weight: 20
--- 

### Login to cluster and extract VERDI software

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`

`cd /shared/build`

`tar -xzvf VERDI_2.1.4_linux64_20230425.tar.gz`


### Run verdi to look at Ozone

```
cd /fsx/data/output/output_v54+_cb6r5_ae7_aq_WR413_MYR_gcc_2018_12US1_3x64_classic/
/shared/build/VERDI_2.1.2/verdi.sh -f $cwd/CCTM_CONC_v54+_cb6r5_ae7_aq_WR413_MYR_gcc_2018_12US1_3x64_classic_20171222.nc -s "O3[1]" -g tile
```

### Run VERDI to look at PM2.5

```
/shared/build/VERDI_2.1.2/verdi.sh -f $cwd/CCTM_AELMO_v54+_cb6r5_ae7_aq_WR413_MYR_gcc_2018_12US1_3x64_classic_20171222.nc
```



