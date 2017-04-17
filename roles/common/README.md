# Common
Ansible Role for the all servers

## Requirements
Ansible version => 2.2

## Role tags:
  - apt - apt-packages setup/update
  - yum - yum-packages setup/update
  - ulimit - set system limits (like open files limit)
  - repos - set common apt/yum repos
  - locales - set default system locales
  
# Vars
## Default role variables
```yaml
country: us
do_upgrade: False

locales:
    - en_US.UTF-8
    - ru_RU.CP1251
    - ru_RU.UTF-8

system_limits:
  ulimits:
    - 'root soft nofile 65536'
    - 'root hard nofile 65536'
    - '* soft nofile 65536'
    - '* hard nofile 65536'

apt_packages:
    - build-essential
    - libssl-dev
    - uuid-dev
    - aptitude
    - bash-completion
    - curl
    - fail2ban
    - git
    - tig
    - htop
    - iputils-ping
    - jnettop
    - less
    - logrotate
    - lsb-release
    - lsof
    - man-db
    - mc
    - netcat
    - postfix
    - rsyslog
    - screen
    - strace
    - sysstat
    - tmux
    - traceroute
    - vim-nox
    - whois
```
## Example Playbook
```yaml
---
- hosts: all
  roles:
    - common
```
# Playbook run
## For all hosts
```
ansible-playbook -i production playbooks/common.yml
```
## For single host
```
ansible-playbook -i develop playbooks/common.yml --limit backend-01
```
