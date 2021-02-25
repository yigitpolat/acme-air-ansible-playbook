# Instructions

```
Clone this repository.

# Confirm you can ssh to managed hosts.
ssh root@148.100.78.207
ssh root@169.50.12.56
ssh root@172.16.28.170

# If not execute below commands.
ssh-copy-id -i ~/.ssh/id_rsa.pub root@148.100.78.207
ssh-copy-id -i ~/.ssh/id_rsa.pub root@169.50.12.56
ssh-copy-id -i ~/.ssh/id_rsa.pub root@172.16.28.170

# Install required collections.
ansible-galaxy collection install -r requirements.yml

# Create container registry secret
ansible-vault create group_vars/all/vault

# container_registry_password: xxx

# Check if everything works fine.
ansible-playbook playbook.yml --syntax-check
ansible-playbook -C playbook.yml --ask-vault-pass

# Execute the playbook
ansible-playbook playbook.yml --ask-vault-pass
```