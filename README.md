# Ansible: Virtual Private Server Setup

Disclaimer:  
This playbook and its roles are only tested for `Ubuntu 22.04` systems!

## Roles

### Hardening

A role to harden your `Ubuntu 22.04` system.  
This role was built using [CIS Ubuntu Linux 22.04 LTS Benchmark v1.0.0](https://workbench.cisecurity.org/benchmarks/10430) as a guide.

Task files contain configuration for:
- AppArmor
- Auditd
- Cron
- Iptables
- journald
- sshd
- sysctl
- timesyncd
- unnecessary services

### Docker

This role installs `docker` and `docker compose`.

## Usage

Install the requirements:
```bash
ansible-galaxy install -r requirements.yml
```

Edit the `inventory` file as needed.  
Edit the `defaults` variables per role as needed.

Execute the whole playbook or selected tasks by setting tags:
```bash
ansible-playbook -i inventory vps.yml
ansible-playbook -i inventory vps.yml --tags "apparmor,sysctl"
```