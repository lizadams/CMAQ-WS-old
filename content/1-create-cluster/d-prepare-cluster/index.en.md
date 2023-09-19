---
title: Prepare cluster and enable X11 display
weight: 23
--- 

Your user should be similar to `ec2-user@ip-<IP-address>`. If it is otherwise something like `sh-4.2` or `ssm-user@<IP-address>`, then run the following command before proceeding:

```bash
sudo su ec2-user
```

![ec2-user](/static/images/1-gettoknow-ec2user.png)

1. **Update Yum**


    ```csh
    sudo yum update
    sudo amazon-linux-extras install epel -y
    ```
2. **Add Firefox Browser**

   ```csh
   sudo amazon-linux-extras install firefox
   ```

3. Install Imagemagick

```csh
sudo yum makecache fast
sudo yum install ImageMagick ImageMagick-devel
```

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
sudo service sshd restart
```

Exit the cluster

`exit`

Relogin to the cluster

`pcluster ssh -v -Y -i ~/cmas.pem --region=us-east-1 --cluster-name cmaq-cluster`

Test display

`display`

