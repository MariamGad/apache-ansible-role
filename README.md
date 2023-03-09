# apache-ansible-role
## Overview
Implementing an ansible role for installing Apache on CentOS 9

---
## Prerequisite
* python3 `sudo yum install python3`
* git `sudo yum install git`
* ansible `sudo yum install epel-release` , `sudo yum install ansible`
---
## Dependencies
### `requirements.yml` file 
```
roles:
  - src: https://github.com/MariamGad/apache-ansible-role.git
```
### `playbook.yml` file
```
- hosts: webservers
  become: yes
  roles:
    - /home/mariam/.ansible/roles/apache-ansible-role
```
---

## Validation
* run `ansible-playbook playbook_file -i inventory_file`\
![image](https://user-images.githubusercontent.com/47721226/224179444-d2dd395a-e0a2-487f-aa04-480eb6ff2013.png)
* run `curl host_IP`\
![image](https://user-images.githubusercontent.com/47721226/224179776-81dc3512-92d9-4d55-b3f0-84aeef02598d.png)



