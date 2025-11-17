# Development Inventory

This folder contains the **Ansible inventory and group variables** for the development environment.  
It defines which Docker containers are managed, how Ansible connects to them, and what department‑specific settings apply.

## Files

- `inventory.yaml`  
  The main inventory file. It lists all managed nodes (e.g. `mng_node1`, `mng_node2`) and specifies:
  - Host address (`127.0.0.1`)
  - Port mapping (`2222`, `2223`, etc.)
  - SSH user (`root`)
  - Path to the private key (`~/.ssh/id_ansible_project`)

- `group_vars/`  
  Contains YAML files with variables for each IT department:
  - `it_data.yaml` → Packages and settings for the IT‑Data container.
  - `it_finance.yaml` → Packages and settings for the IT‑Finance container.
  - Additional files can be added for other departments (e.g. `it_ai.yaml`, `it_wealth.yaml`).

- `README.md` (this file)  
  Explains the purpose of the inventory and how to extend it.

## Purpose

The `inventories/dev` folder allows you to:
- Keep environment‑specific inventories separate (e.g. `dev`, `prod`).
- Define connection details for each container in one place.
- Apply department‑specific configurations automatically via `group_vars`.

## How it works

When you run a playbook with:

```bash
ansible-playbook -i inventories/dev/inventory.yaml playbooks/setup_nodes.yaml
