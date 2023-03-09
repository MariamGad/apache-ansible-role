# apache-ansible-role
## Overview
Implementing an ansible role for installing Apache on CentOS 9
<div align="center">
<img src="https://user-images.githubusercontent.com/47721226/224185901-f065bd02-e4df-4aed-9007-c2bfa1f29c24.png">
<p>Used hierarchy</p>
</div>

---
## Prerequisite
#### On master machine
* Install python3 `sudo yum install python3`
* Install git `sudo yum install git`
* Install ansible `sudo yum install epel-release` , `sudo yum install ansible`
* Set Passwordless authentication between master and hosts `ssh-keygen` , `ssh-copy-id host_name@IP_address`
* Add inventory file has all hosts\
For example:
  ```
  webserver1 ansible_ssh_host=192.168.21.138 ansible_ssh_user=mariam ansible_ssh_private_key_file=/etc/ansible/key.pem
  ```

#### On hosts machines
* in `/etc/sudoers` add `host_name ALL=(ALL) NOPASSWD: ALL`
---
## Dependencies
* ###  `requirements.yml` file 
```
roles:
  - src: https://github.com/MariamGad/apache-ansible-role.git
```
  by default roles are downloaded here `/home/username/.ansible/roles`
* ###  `playbook.yml` file
```
- hosts: webservers
  become: yes
  roles:
    - /home/username/.ansible/roles/apache-ansible-role
```
---

## Validation
* run `ansible-playbook playbook_file -i inventory_file`\
![image](https://user-images.githubusercontent.com/47721226/224179444-d2dd395a-e0a2-487f-aa04-480eb6ff2013.png)
* run `curl host_IP`\
![image](https://user-images.githubusercontent.com/47721226/224179776-81dc3512-92d9-4d55-b3f0-84aeef02598d.png)



