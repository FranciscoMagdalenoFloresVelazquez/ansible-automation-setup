# Ansible Automation Setup

Automated provisioning of Linux environments using Ansible roles for system setup, Docker installation, and development tools.

## Tech Stack

- Configuration Management: Ansible  
- Operating System: Ubuntu Server  
- Containerization: Docker  
- Automation: Bash  
- Remote Access: SSH  

## Objective

This project aims to automate the configuration of multiple Linux nodes in a home lab environment using Ansible, following best practices such as role-based architecture and idempotent tasks.

## Features

- Base system configuration (packages, users, SSH hardening)
- Docker installation and setup
- Development environment provisioning (Neovim, tools)
- Role-based structure for scalability
- Reusable and idempotent playbooks

## Project Structure

ansible-automation-setup/
├── ansible.cfg
├── requirements.yaml
├── README.md
│
├── inventories/
│   └── home_lab/
│       ├── hosts.ini
│       └── group_vars/
│           ├── all.yaml
│           ├── docker.yaml
│           └── dev_env.yaml
│
├── playbooks/
│   ├── setup.yaml
│   ├── docker.yaml
│   └── dev_env.yaml
│
├── roles/
│   ├── common/
│   │   ├── defaults/
│   │   │   └── main.yaml
│   │   ├── vars/
│   │   │   └── main.yaml
│   │   ├── tasks/
│   │   │   ├── main.yaml
│   │   │   ├── packages.yaml
│   │   │   ├── users.yaml
│   │   │   └── ssh.yaml
│   │   ├── handlers/
│   │   │   └── main.yaml
│   │   ├── templates/
│   │   └── files/
│
│   ├── docker/
│   │   ├── defaults/
│   │   │   └── main.yaml
│   │   ├── vars/
│   │   │   └── main.yaml
│   │   ├── tasks/
│   │   │   └── main.yaml
│   │   ├── handlers/
│   │   │   └── main.yaml
│   │   ├── templates/
│   │   └── files/
│
│   ├── dev_env/
│   │   ├── defaults/
│   │   │   └── main.yaml
│   │   ├── vars/
│   │   │   └── main.yaml
│   │   ├── tasks/
│   │   │   └── main.yaml
│   │   ├── handlers/
│   │   │   └── main.yaml
│   │   ├── templates/
│   │   └── files/


## Roles Overview

### common
Handles base system configuration:
- Package installation
- User management
- SSH configuration

### docker
Installs and configures Docker:
- Docker engine installation
- Service management

### dev_env
Sets up development tools:
- Neovim (LazyVim)
- CLI tools
- Ansible

## Usage

Run the main playbook:

```bash
ansible-playbook playbooks/setup.yml

## Requirements

- Ansible installed
- SSH access to target nodes
- Sudo privileges on remote machines

## Configuration

- Inventory: `inventories/home_lab/hosts.ini`
- Default user: defined in `ansible.cfg`

## Future Improvements

- Add CI/CD pipeline
- Integrate cloud provisioning (AWS / Azure)
- Add monitoring setup (Prometheus, Grafana)

## What I Learned

- Structuring Ansible projects using roles
- Writing idempotent automation tasks
- Managing multi-node environments
- Automating development environments
