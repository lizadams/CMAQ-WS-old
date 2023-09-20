---
title: Install VERDI on HPC cluster
weight: 20
--- 

### Login to cluster (if not already logged in)

```csh
pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster
```

### Verify that VERDI is installed

```csh
which verdi.sh
```

### Verify headless display is available

```csh
ls /usr/lib/jvm/java-17-amazon-corretto.aarch64/lib`
```

### If needed, install library for headless display

```csh
wget https://download.oracle.com/java/17/archive/jdk-17.0.8_linux-aarch64_bin.rpm
sudo rpm -ivh jdk-17.0.8_linux-aarch64_bin.rpm
```

