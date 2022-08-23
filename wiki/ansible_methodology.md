## Team Ansible Methodology
Why we use Ansible the way we do.  
 
## Table of contents
* [General Info](#general-info)
* [BNE Ansible Deployment](#bne-ansible-deployment)
* [NextGen ASR Build Process](#nextgen-asr-build-process)
* [Playbook Methodology](#playbook-methodology)

## General info
Ansible uses machine parsable text files (YAML) with vendor Python libraries to push config and show commands to routers and switches.
The Playbooks in this GitHub respository are examples of how to deploy both specific routers configs as well and template config that all devices would have.

*example: interface IP would be specific to router; vty acl would be the same on all routers*
	
## BNE Ansible deployment
Our Ansible playbooks will be used to pre-deploy backbone routers and well as change configurations on our backbone as scale (*vty acl standardization*).
The Production Engineering DevOps team (Automation and Playout) uses a central Ansible server with AWX (*AWX is the open-sources version of RedHat Automation Platform*) with provides a HTTPS based GUI. 

### Production Network Engineering is not going to use the DevOps Ansible deployment, we have built our own.

Why:
* The DevOps ansible has login information for all devices; added as they are needed in a playbook
	* This is a massive inventory list that can be used by the users of the server
* There is no containment mechanism to stop an accidental mass deployment
	* The Production Network Engineering Ansible server is built in AWS, its tied to a NGFW rules to reach our lab and production
	* In addition to a specific inventory list in the Ansible hosts file; the NGFW must also be configured with the IP of the destination routers
		
## NextGen ASR biuld process
The Ansible server on BNE sandbox has Ansible and Git installed.

#### What is Git?
* Git is a distributed, open-source version control system (VCS) that enables you to store code, track revision history, merge code changes, and revert to earlier code version when needed.

Git will give us the abibility to keep network config templates on a team "hub".  It will track changes that are made and by who. 
Git will give the team the ability to work local configs, push to the hub for review, merge changes into master template, and pull the code to the Ansible deployment server.

BNE is going to deploy the NextGen ASR build using a limited Git feature set:
* The team will build and edit Ansible YAML playbooks via our GitHub portal.
* The team will pull those playbooks to the Ansible server and execute to 9902 and 9903 routers rack in the lab environment.

As the team matures in the DevNetOps build cycle we will start working with branch, merge, and other Git operations

Pull request of our GitHub respostiory to Ansible server:
```
git pull git@github.inbcu.com:bne-neteng/aws-lab-bne.git
```


## Playbook methodology

Ansible has been in operation for years; most the vendors we use have open source "Galaxy libriaries" that we can use.
Ansible can integrate with Jinga2; this allows an Ansible text file to be interactive with Python.

The NextGen ASR build is going to start simple; we are going to use two types of playbooks.   One for static "all routers get this" config and another playbook for router specific config.

This is an example of a playbook that *loops* through interfaces to deploy standard config:

```
tasks:
  - name: loop standard config
    ios_config:
      lines:
        - no shutdown
        - mtu 9202
      parents: "{{ item }}"
    loop:
      #with_items:
        - interface vlan12
        - interface vlan22
        - interface vlan32
```
This is an example of a playbook that deploys routers specific config:
```
tasks:
  - name: int description
    ios_config:
      lines:
        - vlan 13
        - name A1-13
        - vlan 23
        - name A2
        # VRF-A1 config
        - interface vlan13
        - vrf member A1
        - ip address 100.123.x.x 255.255.255.248
        # VRF-A2 config
        - interface vlan23
        - vrf member A2
        - ip address 100.123.x.x 255.255.255.248
```
Playbooks can also be *stacked*.  A playbook can be built to call other playbooks.  
```
- import_playbook: metric_before.yml
- import_playbook: te_config.yml
- import_playbook: metric_after.yml
```


#### Ansible server access and playbook execution

SSH to Ansible server:
```
`ssh -i "keypair.pem" ec2-user@x.x.x.x`
```

Executine a playbook:
```
ansible-playbook ./te_chg_books.yml --extra-vars "sso=user pass=pass"
```

