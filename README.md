# Ansible tools for a new Developer

Installing the right software for a new developer joining a company can be very time-consuming. 
What if you could automate the process? Playbook ansible allows you to quickly and automatically install 
and configure the required software for a new Java developer. \
The playbook will include the installation of:
1. GIT
2. Docker
3. Open JDK
4. Maven
5. Intellij IDEA (along with creation a shortcut the application on the desktop)

# REQUIREMENTS
1. Local machine with unix operating system
2. Installed Ansible. If you don't have Ansible on your local machine, follow to instruction -> https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

# RUNNING PLAYBOOK
1. You need to swap values of ansible_host, ansible_ssh_pass and ansible_sudo_pass in inventory file.\
Inventory file is encrypted. You need to decrypt using command: `ansible-vault decrypt inventory` and you need to add ansible vault password **ansible**\
_If you aren't in the same folder as inventory file, you need specify the absolute path to the file_\
_**EXAMPLE** (if you are in roles directory)_ `ansible-vault decrypt ../inventory`\
**!!WARNING!! Inventory file must always be protected. Before making a commit, don't forget to encrypt the inventory file**
_**EXAMPLE** `ansible-vault encrypt inventory` and you will need to enter two times encrypt password


2. You need to swap **ansible_user** value in **roles/dev-tools/vars/main.yml** file

# HERE WE GO!
You can run ansible playbook using command `ansible-playbook main-palybook.yml -i inventory --ask-vault-pass`\
You need to enter a specific password you set when encrypting the inventory file