---
title: Visualize Results using Jupyter Notebook
weight: 20
--- 

For this training, use the DCV.

NICE DCV is a high-performance remote display protocol that provides customers with a secure way to deliver remote desktops and application streaming from any cloud or data center to any device, over varying network conditions.

There are additional methods to create plots of CMAQ Output Data, and some of this is being shared as scripts.
Typically these files end in an extention that reflects their contents as follows:
R (.R), Python (.py), and Jupyter Notebook (.ipynb)

1. **Spatial Plots of Max Percent Differences**

This plot was developed by Sara Farrell from US EPA, modified slightly by Liz Adams as a work-around for not being able to use cut-and-paste functionality in the DCV.
   
2. Main_Purpose

This script works to create spatial difference plots at the date and time where said max percent difference occurs (in both the positive and negative direction) between two CMAQ output files
   
3. Other_Features

a. Works with <font color="teal">**Lambert Conformal**</font> (CONUS and states/localities within) and <font color="purple">**Stereographically**</font> (N. Hemispheric) Projected output

If you need another spatial domain not covered Sara Farrell can add one in!
b.  Showcases colorgrid options
c.  Extracts time, projection, species and units from file headers
d.  Circles the grid cell and area where the max difference occurs
 
4. General Instructions

a) You run each cell by clicking in it and then pressing Enter+Shift
b) You will be prompted to provide some inputs such as color schemes, and time zone information, etc
c) This is in it's beta form so if you have any feedback or need any help feel free to e-mail Sara Farrell (Farrell.Sara@epa.gov) for help



To run the code interactively as a Jupyter Notebook, use the command:

```
cd /path/to/jupter-notbook-location
jupter notebook
```

The jupyter notebook will appear in the web browser on the machine.
