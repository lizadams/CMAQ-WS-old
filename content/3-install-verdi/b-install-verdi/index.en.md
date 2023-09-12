---
title: Install VERDI on HPC cluster
weight: 20
--- 

### Login to cluster and 

```csh
pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster
```

### Install VERDI

```csh
cd /shared/build
wget https://github.com/CEMPD/VERDI/releases/download/2.1.1/VERDI_2.1.4_linux64_20230425.tar.gz
```

### Extract VERDI software

```csh
cd /shared/build
tar -xzvf VERDI_2.1.4_linux64_20230425.tar.gz
```

### Install library for headless display

```csh
wget https://download.oracle.com/java/17/archive/jdk-17.0.8_linux-aarch64_bin.rpm
sudo rpm -ivh jdk-17.0.8_linux-aarch64_bin.rpm
```


### Verify headless display is available

```csh
ls /usr/lib/jvm/java-17-amazon-corretto.aarch64/lib`
```
