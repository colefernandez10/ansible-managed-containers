# Playbooks

This folder contains the **Ansible playbooks** used to configure and manage the Docker containers.  
Playbooks are YAML files that describe a series of tasks Ansible will execute on the managed nodes.

## Files

- `setup_nodes.yaml`  
  A starter playbook that:
  - Updates the apt package cache.
  - Installs department‑specific packages (defined in `group_vars`).
  - Creates a department directory under `/opt/`.

Additional playbooks can be added here for other purposes, such as:
- Configuring web servers.
- Setting up databases.
- Deploying applications.

## Purpose

Playbooks allow you to:
- Automate repetitive tasks across multiple containers.
- Apply department‑specific configurations without duplicating code.
- Ensure idempotency (running the same playbook twice won’t break anything; Ansible only changes what’s needed).

## How it works

When you run a playbook with:

```bash
ansible-playbook -i inventories/dev/inventory.yaml playbooks/setup_nodes.yaml
