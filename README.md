# Ansible Docker Lab

This project demonstrates how to use Ansible from WSL to manage Docker containers.

## Project structure
- `inventories/dev/` → Inventory and group variables
- `playbooks/` → Playbooks to configure containers

## Quick start
1. Spin up Docker containers with SSH enabled.
2. Copy your public key into each container.
3. Run `ansible -i inventories/dev/inventory.yaml all -m ping` to test connectivity.
4. Run `ansible-playbook -i inventories/dev/inventory.yaml playbooks/setup_nodes.yaml` to provision them.
