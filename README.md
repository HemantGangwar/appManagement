![image](https://user-images.githubusercontent.com/38517925/86527948-5f983e80-bec1-11ea-9be7-03a6cc7792c8.png)

# appManagement - For application Management on Nix servers

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

![image](https://user-images.githubusercontent.com/38517925/99140367-6bfa8800-2667-11eb-8291-be4e14f1887d.png)

## **USAGE**:

1. Create host_vars or group_vars directory.

Sample hostvars file:

vi hostvars/sample.yml

> \---  
>  mkt_application_service_list:\
>  \- application1\
>  \- application2\
> ...\
>  \- applicationN

> application_shell_start_commands:\
>  \- command1\
>  \- command2\
> ...\
>  \- commandN

> application_shell_stop_commands:\
>  \- command1\
>  \- command2\
> ...\
>  \- commandN

> application_shell_restart_command:\
>  \- command1\
>  \- command2\
> ...\
>  \- commandN

> application_shell_status_commands:\
>  \- command1\
>  \- command2\
> ...\
>  \- commandN

2. Now create respective hosts or group yaml files as displayed below. Most importantly notice the use of varibles here.

![image](https://user-images.githubusercontent.com/38517925/99140412-e2978580-2667-11eb-89e1-eff50046ef30.png)

**Note**: The name of the YAML files should be same as name of host or group as mentioned in inventory.

## **INVENTORY**:

A sample inventory file given below, we are trying to avoid filling variables here and keeping it simple.

![image](https://user-images.githubusercontent.com/38517925/99140426-022eae00-2668-11eb-9953-3733b32befd3.png)

## **VARIABLES USED**:

Below variables are used innthis playbook and it should be properly understood to use playbook effectively. 


- **mkt_application_service_list** : Applications name list.
- **application_shell_start_commands** : Shell based application start commands.
- **application_shell_stop_commands** : Shell based application stop commands.
- **application_shell_restart_commands** : Shell based application restart commands.
- **application_shell_status_commands** : Shell based application status commands.

## **PLAYBOOK EXECUTION**:

Playbook **generic_application_control.yml** is written in such a way that it won't run without *tags* , so one can use below commands for it's execution:

Index | Action | Commands
----- | ------ | ------
1 | **Starting of applications** | *ansible-playbook -i inventory generic_application_control.yml --tags startup*
2 | **Stopping of applications** | *ansible-playbook -i inventory generic_application_control.yml --tags shutdown*
3 | **Restart  of applications** | *ansible-playbook -i inventory generic_application_control.yml --tags restserv*
4 | **Verification of applications** | *ansible-playbook -i inventory generic_application_control.yml --tags verify*

Author & Maintainer: ***Hemant Gangwar***

To know more about author visit: https://www.linkedin.com/in/hemant-gangwar-6a677b19/
