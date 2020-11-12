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

Note: Always run the playbook by providing specific tags, else it won't run.

Author & Maintainer: ***Hemant Gangwar***
