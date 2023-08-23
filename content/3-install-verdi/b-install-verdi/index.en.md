---
title: Install VERDI on HPC cluster
weight: 20
--- 

### Login to cluster and extract VERDI software

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`

`cd /shared/build`

`tar -xzvf VERDI_2.1.4_linux64_20230425.tar.gz`
