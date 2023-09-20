---
title: Use VERDI to visualize the change in Ozone and PM2.5 due to reducing emissions from PT_EGU sources in New York 
weight: 20
--- 

### Run VERDI to look the change in Ozone

Note, it is difficult to copy and paste content to the NICE DCV.

Please use the following scripted versions.

```csh
cd /shared/pcluster-cmaq/qa_scripts/workshop
```

### Run VERDI to look at the change in PM2.5

```csh
/shared/build/VERDI_2.1.2/verdi.sh -f $cwd/CCTM_AELMO_v54+_cb6r5_ae7_aq_WR413_MYR_gcc_2018_12US1_3x64_classic_20171222.nc
```

### Zoom in to the State of New York

Use your mouse to click and then drag to the right to create a region or use the 

Controls > Set Row and Columns Ranges

Rows: 122, 236
Columns: 319, 402

Select 

Plot > Animate Plot

Then select Start on the Animate Plot window.

An example of this animation is available:

Test

![Change in PM2.5 due to Emission Reduction of PT_EGU in NY](static/images/PM25_NY_PTEGU_EMIS_REDUCED.gif)

