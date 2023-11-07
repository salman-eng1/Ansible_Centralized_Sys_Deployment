
_______________________QMS deployment with Ansible ____________________________

1- install ansible on the master node
2- extract the attached playbooks into /etc/ansible/ 
 - extractthe attached ubuntu_doctor folder to the path /home/master_dir/

3- add the lines below to /etc/ansible/ansible.cfg:
     
     [privilege_escalation]
     become= True
     become_method= sudo
     [defaults]
     Host_key_checking = False
     #ansible_ssh_extra_args='-o StrictHostKeyChecking=no

4- read the file /etc/ansible/hosts, then setup the required information 
5- execute the commands:
-  $ ssh-keygen
-   $ansible-playbook initiate_sshkeys -k –ask-become 
Note: you should navigate to /etc/ansible when executing ansible commands, because ansible coomands are not global
you will be asked for the password for the your account "recommended to use shared username & passwd between all the nodes"
as example:
username: ubuntu
passwd: ubuntu
6- execute the following commands inside /etc/ansible/
$ ansible-playbook deploy_MYSQL.yml --ask-become
$ ansible-playbook deploy_QMS.yml



