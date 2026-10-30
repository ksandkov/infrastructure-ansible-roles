# Ansible Infrastructure Roles

Ansible roles that prepare an Ubuntu server to run an application behind Nginx: base packages, a deploy user, Docker, and an Nginx reverse proxy.

## Roles Overview

* **`common`**: Updates the apt cache, installs base tools (curl, git, ufw, htop, sudo) and creates the `deploy` user.
* **`docker`**: Installs Docker from the Ubuntu packages, starts the service and adds `deploy` to the `docker` group.
* **`nginx`**: Installs Nginx and renders a reverse proxy config from a Jinja2 template; Nginx is reloaded only when the config changes.

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
