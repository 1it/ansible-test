# Scripts 
Ansible common role. Put local backup scripts on servers.

## Requirements
Ansible version => 2.2

## Role tags:

## Default role variables
```yaml
backups_count: 30
```
## Example Playbook
```yaml
---
- hosts: all
  roles:
    - scripts
```
# Playbook run
```
ansible-playbook playbooks/scripts.yml
```
