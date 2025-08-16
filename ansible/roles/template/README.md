# Ubuntu Server Raw Template

**Foundation Layer**: Universal base template for ALL virtual machines. (servers and desktops)

## Overview

This template creates the fundamental foundation that every VM in the infrastructure builds upon. It establishes the core system configuration, security, and essential services required by all machines.

## System Configuration

### Security & Trust
- **Homelab CA Certificate**: Installs custom certificate authority for internal services.
- **IPv6 Disable**: Disables IPv6 system-wide for security and compatibility.

### Time & Location
- **Timezone**: Configures Brazilian timezone (America/Sao_Paulo).
- **NTP Servers**: Sets up Brazilian NTP servers for accurate time synchronization.

### System Services
- **Cloud-Init**: Enables cloud-init for VM provisioning automation.
- **Hardware Hotplug**: Enables dynamic hardware addition/removal.
- **GRUB Boot Menu**: Configures boot menu timeout settings.
- **Network Interface Names**: Sets predictable network interface naming.

## Package Installation

### Core System Packages
- `sudo` - Administrative privileges.
- `qemu-guest-agent` - Enhanced Proxmox VM integration.
- `openssh-server` - Remote SSH access.
- `cloud-init` - VM initialization service.

### Python Environment
- `python-is-python3` - Python 3 as default Python.
- `pipx` - Isolated Python package management.
- `python3-psutil` - System information library.
- `python3-passlib` - Password hashing with bcrypt.
- `python3-jmespath` - JSON query expressions.

### Hardware & Drivers
- `ubuntu-drivers-common` - Latest hardware driver support.

## User Management
- **Ansible User**: Creates dedicated automation user account.
- **SSH Configuration**: Sets up default SSH client configuration.

## System Cleanup
- **Package Removal**: Removes unnecessary packages to minimize footprint.
- **Machine-ID Reset**: Generates new machine-ID for unique VM identity.
- **Log Cleanup**: Removes installation logs and temporary files.

#
### Created by:

1. Luciano Sampaio.
