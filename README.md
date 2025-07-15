# Ansible Sysadmin Playbooks

This repository contains a collection of Ansible playbooks I've created and actively use in my day-to-day work managing Linux servers. These playbooks automate essential sysadmin tasks, improving consistency, speed, and reliability across environments.

## Playbooks Included

### 🔹 1. Netcat Connectivity Check (`netcat_check.yml`)
This playbook uses `nc` (netcat) to test connectivity to a list of target IP addresses on port **443**. It's useful for verifying firewall rules, load balancer reachability, or external service availability.

**Example use case:**  
Testing which internal servers have outbound access to the internet via HTTPS.

### 🔹 2. Bulk User Creation (`create_users.yml`)
Creates multiple Linux user accounts, sets their passwords (username = password), forces password change on first login, and optionally adds them to the `wheel` (sudo) group.

**Features:**
- Idempotent
- Secure password enforcement
- Easily scalable

### 🔹 3. Patch Management (`patch_servers.yml`)
Applies security and system updates across Red Hat-based systems. Can be scheduled during maintenance windows or triggered manually.

**Goal:** Keep systems patched and compliant without logging into each server manually.

## 🔧 Requirements

- Ansible 2.9+  
- SSH access to target hosts  
- Inventory file or dynamic inventory configured  
- `become: true` (for privilege escalation on most tasks)

## 📦 How to Use

1. Clone this repo:

```bash
git clone https://github.com/yourusername/ansible-sysadmin-playbooks.git
cd ansible-sysadmin-playbooks
