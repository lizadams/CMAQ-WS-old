---
title: Run CMAQ on the HPC7g Cluster
weight: 23
---

:::alert{type=info}
The CMAQ run script has been configured to run on 192 cores (3 compute nodes of hpc7g with 64 cores/node)
:::


1. **Change directories to the run script location**

```csh
cd /shared/build/openmpi_gcc/CMAQ_v54+/CCTM/scripts
```

2. **Edit the run script (`run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.csh`) to only run for 1 day**

```csh
perl -i -pe ' \
  s/(#SBATCH -o)(.*)2day(.*)/${1}${2}1day${3}/; \
  s/(#SBATCH -e)(.*)2day(.*)/${1}${2}1day${3}/; \
  $d = qr/"\d{4}-\d{2}-\d{2}"/; \
  $s = $1 if /set START_DATE = ($d)/; \
  s/(\s+set\sEND_DATE\s+=)\s+$d(.*)/\1 ${s}\2/; \
  ' run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.csh
```

2. Load the Environment Modules

```csh
module load gcc/gcc-9.3 ioapi-3.2/gcc-9.3-netcdf netcdf-4.8.1/gcc-9.3
```

3. **Submit the Run script to the SLURM queue**

```csh
sbatch run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.csh
```

4. **Check the status of the job**

```csh
squeue
```

Output

```
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
                 1   compute     CMAQ   ubuntu CF       0:30      3 compute-dy-hpc7g-[1-3]
```

Wait for the status to change from CF to R

4. **Login to the compute node and run htop**

```csh
ssh -Y compute-dy-hpc7g-1
htop
```

![ec2-user](/static/images/2-run-cmaq-htop.png)

5. HTOP should show that 64 processes are running and that 80.2G out of 124 G of memory is being used.


