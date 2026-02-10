# Ansible Infrastructure Roles

Production-ready Ansible collection for configuring bare-metal Linux servers with Security hardening, Docker, and Nginx Reverse Proxy.

## Roles Overview

* **`common`**: Security baseline, UFW firewall rules, essential tools, and system users.
* **`docker`**: Docker Engine setup and group permissions.
* **`nginx`**: Automated Reverse Proxy setup using Jinja2 dynamic templates.

## Project Structure

```text
. 
├── group_vars/       # Group-specific variables
├── inventory.ini    # Server management inventory
├── roles/            # Modular infrastructure roles
│   ├── common/
│   ├── docker/
│   └── nginx/
└── site.yml          # Main entrypoint playbook
```

## Usage

1. Update target IPs in `inventory.ini`.
2. Configure variables in `group_vars/webservers.yml`.
3. Run the playbook:

```bash
ansible-playbook -i inventory.ini site.yml
```
