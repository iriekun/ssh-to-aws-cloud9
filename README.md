# ssh-to-cloud9

How to Connect to Cloud 9 Via SSH

1. Create a keypair from AWS console e.g YOUR_KEY.pem</br>
2. Generate public key from your existing keypair on local terminal 
```
ssh-keygen -f YOUR_KEY.pem -y
```
Output should be something similar to below
```
ssh-rsa 
AAAAB3NzaC1yc2EAAAADAQABAAABAQDWGRZsPraV6v4UqfZTFKAXK9bhjWVkONEKyAA1CeOkxSN+9WdY7gKgjbPOeUx3LFqRudBvSrP+eKTtthPrl Nx9UBvXniVK252i4h0xnIcrRO1PUpq0EzyqX+n3u2YwytT+on6x98PRjtD4oCKyfFviWBqnRHtWvRre8CWhULuJrmUeo2aPrVTPXo/TwJpZupXv63YyUMPC 2wyDMDsKNZhsqUedkJ8575PGXCg9gEkPg2ulR8NUrzDSfbXIrZLgCcIziwDQ0dA9B28OAQ9saPyXYzrZF1ZmCxKgzSHHiKdBAJ0E/X/s53N5Hg04SIWy4D4lMT 9g+AZG38YPNq68mo4b
```
3. In cloud 9 instance, click on <i>setting</i>, <i>show home in favorite </i> and <i> show hidden files</i>
4. Expand .ssh folder, open <i>authorized_keys file</i> and paste the public key
5. Go to local terminal and type 
```
ssh -i YOUR_KEY.pem ec2-user@CLOUD9-PUBLIC-IP -L 5000:localhost:5000
```
Remember to replace CLOUD9-PUBLIC-IP with your cloud9 public IP
