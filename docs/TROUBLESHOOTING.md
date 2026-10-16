# Issues encountered and resolutions

This document summarizes problems and fixes described in the Week 12 assignment. Some problems appeared during setup and were resolved before the final screenshot evidence.

### SSH connection timeout

**Reported resolution:** Previous lab infrastructure had been destroyed; redeployed Azure VMs and updated the inventory with current addresses.

### First-time SSH host prompt

**Reported resolution:** Verified/accepted host keys.

### APT package 404

**Reported resolution:** Updated package cache before installing Nginx.

## Diagnostic approach

1. Start with the failing Terraform/Ansible command and its exact error output.
2. Check inventory, network reachability, SSH access and the current cloud resource IPs.
3. Review Ansible play recap or Terraform plan and make the smallest justified change.
4. Rerun validation and collect fresh evidence before claiming success.
