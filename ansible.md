Getting started with Ansible involves several steps, including setting up your environment, writing your first playbook, and running your first commands. Here's a step-by-step guide to help you get started:

### 1. Install Ansible

#### On Ubuntu/Debian:
```bash
sudo apt update
sudo apt install ansible
```

### 2. Verify Installation
Check the installed version to verify the installation.
```bash
ansible --version
```

### 3. Configure Your Inventory
Ansible uses an inventory file to manage the list of hosts. Create a simple inventory file (`hosts.ini`):
```ini
[webservers]
server1.example.com
server2.example.com

[dbservers]
db1.example.com
db2.example.com
```

### 4. Test Connection
Ensure you can connect to your hosts. You might need to configure SSH keys for passwordless login.
```bash
ansible all -m ping -i hosts.ini
```

### 5. Write Your First Playbook
Create a playbook (`playbook.yml`). Playbooks define the tasks you want to execute on your managed nodes.
```yaml
---
- name: Update and upgrade servers
  hosts: all
  become: yes

  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Upgrade all packages
      apt:
        upgrade: dist
```

### 6. Run Your Playbook
Execute your playbook using the `ansible-playbook` command.
```bash
ansible-playbook -i hosts.ini playbook.yml
```

### 7. Explore Ansible Modules
Ansible has a wide range of modules to perform various tasks. For example, to install a package, you can use the `apt` module (for Debian-based systems) or the `yum` module (for Red Hat-based systems).


pip install boto3
ansible-galaxy collection install community.aws
aws configure

#### 9. Create and run the Ansible Playbook
ansible-playbook list_ec2_instances.yml
ansible-playbook list_all_sgs.yml

Remember to set the aws region and profile
