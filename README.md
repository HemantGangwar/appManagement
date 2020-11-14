![image](https://user-images.githubusercontent.com/38517925/86527948-5f983e80-bec1-11ea-9be7-03a6cc7792c8.png)

# appManagent - For application Management on Nix servers

This **Ansible** playbook is meant to do following tasks on EL6/EL7 onwards systems:

- Stop, Start, Restart, Status of
  - sysvinit
  - systemd
  
- Executing shell base commands for applications stop/start

## **Playbook Structure**:

It is divided in following structure:

1. Main Playbook --> generic_application_control.yml
2. Supporting tasks file --> application-restart.yml , application-start.yml , application-stop.yml , application-verify.yml
3. Variable placement --> host_vars or group_vars
4. Inventory file --> Inventory

![image](https://user-images.githubusercontent.com/38517925/98974756-4708f680-253b-11eb-8276-106ad5253412.png)

## USAGE

1. Create host_vars or group_vars directory.
2. Now create respective hosts or group yaml files as displayed below:

**Note**: The name of the YAML files should be same as name of host or group as mentioned in inventory.

## INVENTORY

A sample inventory file given below, we are trying to avoid filling variables here and keeping it simple.

Author & Maintainer: ***Hemant Gangwar***
