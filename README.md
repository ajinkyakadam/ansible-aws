## Using Ansible and AWS to create a CI CD pipeline for Static Website

<img src="StaticSite.png">

### Pre-Requisites:
Here we assume you have the following on your local machine
 - boto
 - python2.7
 - keys placed in `~/.boto`
 - ansible

### Instructions to Run

`deploy-webapp.yml` playbook does the following as of now:

- create a security group named my-sec-grp which allows ssh, http, https
from any ip address.
- create two ec2 instances named `server1` and `server2`  

Before running add the following to `/etc/ansible/hosts`

```
[local]
localhost
```

To Deploy, execute the following

```
ansible-playbook -i /etc/ansible/hosts deploy-webapp.yml
```

### Work Done:
- role to create ec2 instances
- role to create a security group


### TODO:
- Install the required LAMP stack on the nodes
- role to deploy `nagios` on nagios sever instance and `nrpe and nagios plugins` on the nodes to monitor
- role to create an ELB using `ec2_elb_lb`


#### Author:
Ajinkya Kadam
