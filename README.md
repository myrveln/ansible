# Ansible Arch Linux base repository

This repository is only intended for my own personal usage. Feel free to copy parts into your own environment.
Tested and used with Ansible 2.18.7 and Python 3.13.5.

## Examples

List all available tasks
```bash
ansible-playbook -i inventory/hosts playbook.yml -K -u ssh_username --list-tasks
```

Run tasks with specific tag(s)
```bash
ansible-playbook -i inventory/hosts playbook.yml -K -u ssh_username --tags "base"
ansible-playbook -i inventory/hosts playbook.yml -K -u ssh_username --tags "base,aur"
```

Run the playbook except tasks with tag(s)
```bash
ansible-playbook -i inventory/hosts playbook.yml -K -u ssh_username --skip-tags "aur"
```

Run the playbook with Ansible Vault file, and a secrets file
```bash
ansible-playbook -i inventory/hosts playbook.yml -u ssh_username -K --tags certs --vault-password-file .vault.txt
```

# Generate Ansible Vault credentials file

Obtain the API key from your Jenkins user.

Your user -> Security -> Add new token

## Create a new file with the following contents

Place the file at inventory/group_vars/all/vault.yml

```bash
jenkins_user: admin
jenkins_token: abc_abc123yourRealJenkinsTokenHere
```

## Encrypt the file with Ansible Vault

```bash
ansible-vault encrypt inventory/group_vars/all/vault.yml
```
