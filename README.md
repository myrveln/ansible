# Ansible Arch Linux base repository

This repository is only intended for my own personal usage. Feel free to copy parts into your own environment.
Tested and used with Ansible 2.15.5 and Python 3.11.6.

### Examples

List all available tasks
```
$ ansible-playbook -i inventory/hosts playbook.yml -K -u kim --list-tasks
```

Run tasks with specific tag(s)
```
$ ansible-playbook -i inventory/hosts playbook.yml -K -u kim --tags "base"
$ ansible-playbook -i inventory/hosts playbook.yml -K -u kim --tags "base,aur"
```

Run the playbook except tasks with tag(s)
```
$ ansible-playbook -i inventory/hosts playbook.yml -K -u kim --skip-tags "aur"
```
