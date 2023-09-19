---
title: Review CTM_LOG file for definition of Regions Available for Scaling and Emission Stream Family Definitions
weight: 23
---

:::alert{type=info}
The CMAQ run script has been configured to run on 192 cores (3 compute nodes of hpc7g with 64 cores/node)
:::


1. **Review the Emissions Scaling Report Section in the CTM_LOG File to verify that for the NY region, the EGU emissions were scaled by 75%**

```csh
cd output_v54+_cb6r5_ae7_aq_WR413_MYR_gcc_2018_12US1_3x64_classic_DESID_REDUCE
grep -A 20 'Stream Type: "Point Emissions File   2' CTM_LOG_001*
```

Output:

```csh
     Stream Type: "Point Emissions File   2" | Sector Label: PT_EGU (04)

        Table of Aerosol Size Distributions Available for Use Sector-Wide.
        Note that Mode 1 is reserved for gas-phase species and emission variable.
          Number  Em. Var.  Mode  Reference Mode (see AERO_DATA.F)
          ------  --------------  --------------------------------
          2       FINE                        FINE_REF
          3       COARSE                    COARSE_REF

        CMAQ Species     Phase/Mode  Em. Var.          Region             Op ScaleFac Basis FinalFac
        ------------     ----------  ---------         ------             -- -------- ----- --------
          NO2              GAS        NO2              EVERYWHERE         a   1.000    UNIT   1.000
                                                       NY                 o   0.750    UNIT   0.750
          NO               GAS        NO               EVERYWHERE         a   1.000    UNIT   1.000
                                                       NY                 o   0.750    UNIT   0.750
          HONO             GAS        HONO             EVERYWHERE         a   1.000    UNIT   1.000
                                                       NY                 o   0.750    UNIT   0.750
          SO2              GAS        SO2              EVERYWHERE         a   1.000    UNIT   1.000
                                                       NY                 o   0.750    UNIT   0.750
          SULF             GAS        SULF             EVERYWHERE         a   0.000    UNIT   0.000
                                                       NY                 o   0.750    UNIT   0.750
```

2. **Submit the Run script to the SLURM queue**
```csh
sbatch run_cctm_2018_12US1_v54_cb6r5_ae6.20171222.3x64.ncclassic.DESID_RED_NY.csh
```

3. **Check the status of the job**

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
