---
title: Run Jupyter Notebook to analyze difference between with DESID Emissions and the base case (no emission reduction) 
weight: 20
--- 

###  Connect to the NICE DCV 

1. Select Activities, then click on Terminal Image (MATE Terminal)



2. Change directories to the location of the Jupyter Notebook 

```csh
cd /shared/pcluster-cmaq/qa_scripts/workshop
```

3. Run Jupyter Notebook 

```
Jupyter Notebook
```

4. Select the Spatial_Plots_of_Max_Conc_Differences.ipynb notebook

5. In each cell you can use the 'shift return'  or 'shift enter' to run each cell

6. In the section "Set up your Inputs" you will use shift+enter, then enter the value, and then enter to submit the answer.

7. After the last cell is run, you should see output such as: 

There are no differences in GLYD, ..

8. Go to the output directory and use display to visualize the results

```csh
/fsx/data/output/images/
display NH3_difference_between_Base_Case_vs_Sens_Case_on_12-22-2017_14:*
```
