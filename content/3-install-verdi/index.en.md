---
title: Install VERDI on HPC cluster
weight: 20
--- 

###  Install X-11 Display

1. Update package manager

`sudo apt-get update`

2. Install Imagemagick

`sudo apt-get install imagemagick`

3. Install X11-apps

`sudo apt install x11-apps`

4. Enable X11 forwarding

```
sudo vi /etc/ssh/sshd_config
```

add line

```
X11Forwarding yes
```

Verify that it was added

```
sudo cat /etc/ssh/sshd_config | grep -i X11Forwarding
```

Restart ssh

```
sudo service ssh restart
```

Exit the cluster

`exit`

Relogin to the cluster

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`

Test display

`display`

Output

### logout of cluster and then install VERDI from your local laptop

`exit`

From your local machine 

`scp -i ~/cmas.pem VERDI_2.1.4_linux64_20230425.tar.gz ubuntu@54.80.227.174:/shared/build`


### Login to cluster and extract VERDI software

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`

`cd /shared/build`

`tar -xzvf VERDI_2.1.4_linux64_20230425.tar.gz`


