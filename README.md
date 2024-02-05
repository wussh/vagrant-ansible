# Ansible Project Documentation

## Overview

Briefly describe the purpose and scope of your Ansible project.

## Usage

### SSH Key Generation

Generate an SSH key pair:

```bash
ssh-keygen
```

### Copy Public Key to VMs

Manually add the public key to `authorized_keys`:

```bash
nano ~/.ssh/authorized_keys
# Paste the content of public key, save, and exit
```

### Verify SSH Connectivity

Ensure SSH connectivity to all hosts:

```bash
ansible -i inventory/vagrant all -a "df -h"
```

### Execute Nginx Playbook

Run the nginx playbook:

```bash
ansible-playbook -i inventory/vagrant provision/nginx.yaml
```

## Roles

### Nginx Role

This role is responsible for configuring and managing Nginx.

#### Variables

- `nginx_version`: Specify the version of Nginx to install.

#### Example Playbook

```yaml
---
- hosts: nginx_servers
  roles:
    - role: nginx
      nginx_version: "latest"
```