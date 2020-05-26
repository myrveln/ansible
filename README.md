# Ansible Arch Linux base repository

Tested and used with Ansible 2.9.6 and Python 2.7.10

### Examples

List all available tasks
```
$ ansible-playbook -i inventory/hosts playbook.yml -K --list-tasks
```

Run tasks with specific tag(s)
```
$ ansible-playbook -i inventory/hosts playbook.yml -K --tags "base"
$ ansible-playbook -i inventory/hosts playbook.yml -K --tags "base,aur"
```

Run the playbook except tasks with tag(s)
```
$ ansible-playbook -i inventory/hosts playbook.yml -K --skip-tags "aur"
```
