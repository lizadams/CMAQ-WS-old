---
title: Run CMAQ on the HPC7g Cluster
weight: 23
---

:::alert{type=info}
The CMAQ run script has been configured to run on 192 cores (3 compute nodes of hpc7g with 64 cores/node)
:::


1. **Change directories to the run script location**

`cd /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts`

2. **Edit the run script to only run for 1 day**

Change the log file name to use 1day rather than 2day in the name:

```
#SBATCH -o /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts/run_cctm5.4+_Bench_2018_12US1_cb6r5_ae6_20200131_MYR.192.12x16pe.1day.20171222start.3x64.log
#SBATCH -e /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts/run_cctm5.4+_Bench_2018_12US1_cb6r5_ae6_20200131_MYR.192.12x16pe.1day.20171222start.3x64.log
```


Change the END_DATE to be the same as the START_DATE, to run for only one day

```
#> Set Start and End Days for looping
 setenv NEW_START TRUE             #> Set to FALSE for model restart
 set START_DATE = "2017-12-22"     #> beginning date (January 22, 2017)
 set END_DATE   = "2017-12-22"     #> ending date    (December 31, 2018)
```


2. **Submit the Run script to the SLURM queue**

`sbatch run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.csh`

3. **Check the status of the job**

`squeue`

Output

```
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
                 1   compute     CMAQ   ubuntu CF       0:30      3 compute-dy-hpc7g-[1-3]
```

Wait for the status to change from CF to R

4. **Login to the compute node and run htop**

```
ssh -Y compute-dy-hpc7g-1
htop
```

![ec2-user](/static/images/2-run-cmaq-htop.png)

5. HTOP shows that 64 processes are running and that 80.2G out of 124 G of memory is being used.


