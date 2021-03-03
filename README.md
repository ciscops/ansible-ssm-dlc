# ansible-ssm-dlc
This repo contains an Ansible playbook to automate device led conversion with SSM OnPrem . The intended audience for this playbook is any organization which requires license conversion from traditional PAK keys to Smart licensing. 

## Prerequisites
The following tool(s) will need to be installed on your system:
  - Ansible (Required to run Ansible playbooks.  The install instructions here:  https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Update Inventory File
A sample inventory file is included.  Prior to running the playbook, you will need to update the host, username, and password variables to match your environment. If you have multiple devices, they will have to be uniquely identified per host. For example, having two hosts named ```CSR1``` could lead to unexpected behavior. You could avoid this issue by having one host named ```CSR1``` and the other as ```CSR2```, etc.

## SSM OnPrem DLC
Prior to running the playbook, you will need to update the ```satellite_ip``` variable to be reflective of your environment. Once the steps that has been completed you can run the playbook with this command: 

```
ansible-playbook dlc.yml -e idtoken=<idtoken_from_ssm_onprem>
```
## Synchronize SSM OnPrem
Once the device portion of the process is complete you will need to go in to the User Interface of your SSM OnPrem and initiate a full synchronization in the Admin Workspace.  Depending on your number of devices it can take up to 2 hours to process the changes at software.cisco.com.  Once the licenses are converted, you can check progress in the "Conversion" section of the Virtual Account associated with the OnPrem, then do another full synchronization and your conversion will be complete.  

You can find the latest SSM OnPrem User Guide here:  https://software.cisco.com/download/home/286285506/type/286326948
