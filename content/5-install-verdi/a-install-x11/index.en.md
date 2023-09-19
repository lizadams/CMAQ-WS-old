---
title: Install X11 and Display
weight: 20
--- 

###  Install X-11 Display

1. Update package manager

`sudo yum update`

2. Install Imagemagick

```csh
sudo yum makecache fast
sudo yum install ImageMagick ImageMagick-devel
```

3. Enable X11 forwarding

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
sudo service sshd restart
```

Exit the cluster

`exit`

Relogin to the cluster

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`

Test display

`display`
