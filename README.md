# How to set up server, circleci and code-deploy

## set up new server
1. Spin up a new ubuntu 16.04 box
2. Save pem file
3. Set up .ssh/config file with details something like:

```
Host hostname
        User ubuntu
#       aws long external hostname is too long so change dns or use ip address
        Hostname <amazon-external-ip>
        IdentityFile /route/to/pem/file.pem
        ServerAliveInterval 100
```

4. Install Python on the aws server to allow Ansible to communicate with it
5. Build the host with ansible 
6. Ensure the security group has http/s open
7. Ensure code is pushed to github