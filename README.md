# Ansible playbook for building HTTP server
This Ansible playbook installs and configures the httpd server. And,it installs the "srpm2html" and Web content.

# Install
`git clone git@github.com:Noppy/ansible-BuildWebServer.git` 

# Setup
## Inventory
(1) Make a Inventory file  
create a "inventory" file on the play-book root directory.
```
cd ansible-BuildWebServer
vi inventory
```
(2) Regist ansible agent servers.  
The following sample is for the aws ec2 server.("xxxxx" is ip or DNS name.) 
```
[webservers]
xxxxxxxxxxxxxx ansible_ssh_user=ec2-user
````
## Set PairKey(SSH identity file)
Set aws pair key at ".ssh" directory
```
cat > ~/.ssh/aws_id_rsa
<< PASET PairKey >>
chmod 600 ~/.ssh/aws_id_rsa
```

## execute ansible play-book
```
ansible-playbook site.yml -i inventory --private-key ~/.ssh/aws_id_rsa 
```
