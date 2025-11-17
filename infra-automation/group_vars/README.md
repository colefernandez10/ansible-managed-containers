# Group Vars for IT Department Infrastructure

This folder contains **group variable files** used by Ansible.  
Each file defines packages and settings that are specific to a particular IT department’s Docker container infrastructure.

- `it_data.yaml` → Variables for the IT-Data department (e.g. Python, Git, jq).
- `it_finance.yaml` → Variables for the IT-Finance department (e.g. MySQL client, Curl).

## Purpose
The `group_vars` folder allows you to:
- Manage configuration separately for each department.
- Deploy package updates uniquely across different IT department containers.
- Keep playbooks simple by referencing variables instead of hardcoding packages.

## How it works
When you run a playbook against a host in a group (e.g. `it_data`), Ansible automatically loads the corresponding variables from this folder.  
This makes it easy to scale and maintain department-specific infrastructure without duplicating tasks.
