---
title: Prepare cluster
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
2. **Enable X11 Display**

   ```csh
   sudo yum makecache fast
   sudo yum install ImageMagick ImageMagick-devel
   ```

3. Add 

   ```csh
   sudo vi /etc/ssh/sshd_config
   ```

4. **Add Firefox Browser**

   ```csh
   sudo amazon-linux-extras install firefox
   ```
