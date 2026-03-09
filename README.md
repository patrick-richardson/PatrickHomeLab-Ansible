# PatrickHomeLab Infrastructure Automation

Infrastructure automation and systems management for PatrickHomeLab using Ansible, Proxmox virtualization, and Prometheus monitoring.

## Purpose

This project serves two primary purposes:

• Automate infrastructure management within PatrickHomeLab 
• Develop and demonstrate Systems Engineering and DevOps automation skills

## Infrastructure Overview

Environment Architecture:

Internet 
→ ISP Router 
→ Eero Gateway 
→ Managed Switch 
→ PatrickHomeLab Nodes

Core Systems:

Forge 
Proxmox hypervisor hosting lab virtual machines

Vault 
Network storage server providing NFS media and backup storage

Media VM 
Plex media server deployed as a Proxmox virtual machine

Monitor-01 
Prometheus and Grafana monitoring system

Controller-01 
Primary Ansible automation controller

## Automation Goals

• Automated system updates 
• Infrastructure rebuild capability 
• Monitoring integration 
• Configuration standardization 
• Disaster recovery documentation

## Example Usage

Run update automation:

## How to run (from ~/ansible)
- Audit: `make audit`
- Baseline: `make baseline`

## playbooks/audit.yml
Purpose: Read-only audit (hostname, uptime, disk)
Safe anytime: Yes
Command:
ansible-playbook playbooks/audit.yml

## playbooks/baseline.yml
Purpose: Updates + common packages + ensure SSH running
Safe anytime: Yes (idempotent)
Command:
ansible-playbook playbooks/baseline.yml
