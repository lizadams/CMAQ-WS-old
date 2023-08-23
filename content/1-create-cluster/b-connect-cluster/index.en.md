---
title: Connect to the cluster
weight: 22
--- 

#### Option 1: SSM Connect 

1. After cluster creation completes, with the created cluster selected, choose **Shell** to access the cluster head node.

    ![Connect cluster - shell](/static/images/1-connectcluster-shell.png)


#### Option 1: CLI Connect

1. Use the ParallelCluster Command Line Interface to connect from your computer to the cluster.

`source ~/apc-ve/bin/activate\nsource ~/.nvm/nvm.sh`

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`



