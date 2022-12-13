## Problem statement
Configure Ansible server on VM 1 to deploy a webserver to VM2 and VM3 on port 8080 that displays the message: “Hello World from SJSU-X”, where X is 1 or 2 depending on which webserver.

## Implementation:


* ###  Step 1:
 Deployed 2 ubuntu servers on AWS and one on local machine below are the details.
1. Host server/ansible server - on local machine: Public IP address: 71.198.224.17 ,
    Private IP address: 192.168.118.255 (hegde@ubuntu)
2. Server-1: ec2-54-241-204-15.us-west-1.compute.amazonaws.com
3. Server-2: ec2-54-176-228-75.us-west-1.compute.amazonaws.com



* ### Step 2:
Generated 2048-bit SSH-2 RSA key pair for login while deploying webserver instances
on AWS EC2


* ###  Step 3:
Installed Ansible on host ubuntu machine:
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install ansible
```

* ###  Step 4:
Added servers to the hosts file:
```
[webservers]
 ec2-54-241-204-15.us-west-1.compute.amazonaws.com
 ec2-54-176-228-75.us-west-1.compute.amazonaws.com
 ```

* ###  Step 5:
Made changes to **ansible.cfg file**:
added private Key path.

* ### Step 6:
Checked the connectivity

* ###  Step 7:
Created two playbooks

* ###  Step 8:
using **deploy-webserver.yml** installed apache2 service , copied modified index file and modified default config to listen on port 8080 and then start apache2 service

* ###  Step 9:
using **undeploy-webserver.yml** stopped apache2 service and uninstalled aphache2

## Reference:
[Ansible document](https://docs.ansible.com/)
