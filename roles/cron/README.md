# Cron
Ansible Role for the backend/db servers.
Setup common and custom cron-jobs, like backup and application backgroud tasks.

## Requirements
Ansible version => 2.2

## Role dependencies
```yaml
dependencies:
  - { role: scripts }
```

## Role tags:
  
# Vars
## Default role variables
```yaml
cron_common_jobs: []

cron_backup_jobs:
    - { name: 'mysql_backup.sh', job: 'bash /root/scripts/mysql_backup.sh', minute: 0, hour: 2 }
    - { name: 'local_backup.sh', job: 'bash /root/scripts/local_backup.sh', minute: 30, hour: 2 }

cron_custom_jobs: []
```
## Example Playbook
```yaml
---
- hosts: backend
  roles:
    - cron
```
# Playbook run
## For all hosts
```
ansible-playbook -i production playbooks/cron.yml
```
## For single host
```
ansible-playbook -i develop playbooks/cron.yml --limit develop
```
