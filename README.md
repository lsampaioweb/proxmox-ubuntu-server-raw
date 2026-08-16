# proxmox-ubuntu-server-raw

Minimal Ubuntu template automation for Proxmox using Packer and Ansible.

## Quick Start

```bash
# Clone repository
git clone --recurse-submodules https://github.com/lsampaioweb/proxmox-ubuntu-server-raw.git
cd proxmox-ubuntu-server-raw

# Build with Packer (Proxmox)
cd packer
packer build -var-file="env/homelab/vars.pkrvars.hcl" config.pkr.hcl

# OR configure with Ansible (VirtualBox/custom)
cd ansible
ansible-playbook template.yml -e "password_id=ubuntu-24-04-server-raw"
```

## What's Included

- **Packer** - Build Ubuntu images from ISO
- **Ansible** - Configure VMs with essential packages and security
- **Roles** - Modular configuration (common, template, kvm_setup)
- **Cloud-Init** - VM provisioning support

## Key Features

✓ Minimal footprint (essential packages only)
✓ Idempotent automation (safe to re-run)
✓ Security hardened (SSH, CA certs, IPv6 disabled)
✓ Cross-platform (Proxmox, VirtualBox, KVM)
✓ Secrets in system keyring (no hardcoded credentials)

## Directory Structure

```
ansible/          Playbooks and roles
packer/           Packer build configuration
  iso/            ISO build details
  env/            Environment variables
```

## Documentation

- **Ansible** → [ansible/README.md](ansible/README.md)
- **Packer** → [packer/README.md](packer/README.md)

## Prerequisites

- Proxmox VE, VirtualBox, or KVM hypervisor
- Packer (for building) or Ansible 2.10+ (for manual setup)
- Git

## Support

For issues: Check [packer/README.md](packer/README.md) or [ansible/README.md](ansible/README.md) for detailed troubleshooting.

## License

MIT
Author: Luciano Sampaio
