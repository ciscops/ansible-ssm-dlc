# ansible-ssm-dlc
This repo contains an Ansible playbook to automate device led conversion with SSM OnPrem . The intended audience for this playbook is any organization which requires license conversion from traditional PAK keys to Smart licensing. 

## Prerequisites
The following tool(s) will need to be installed on your system:
  - Ansible (Required to run Ansible playbooks.  The install instructions here:  https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Update Directory File
A sample inventory file is included.  Prior to running the playbook, you will need to update the host, username, and password variables to match your environment. If you have multiple devices, they will have to be uniquely identified per host. For example, having two hosts named ```CSR1``` could lead to unexpected behavior. You could avoid this issue by having one host named ```CSR1``` and the other as ```CSR2```, etc.

## SSM OnPrem DLC
Prior to running the playbook, you will need to update the ```satellite_ip``` variable to be reflective of your environment. Once the steps that has been completed you can run the playbook with this command: 

```
ansible-playbook dlc.yml -e idtoken=<idtoken_from_ssm_onprem>
```
