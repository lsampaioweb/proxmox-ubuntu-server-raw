# Ansible Automation

Ansible playbooks for Ubuntu template and VM configuration.

## Quick Start

```bash
cd ansible

# Configure template
ansible-playbook template.yml -e "password_id=ubuntu-24-04-server-raw"

# Configure Proxmox VM
ansible-playbook kvm_setup.yml -e "node=proxmox-node vm_name=ubuntu-raw cpu_type=x86-64-v2-AES hotplug=disk,network,cpu"

# Configure local machine
ansible-playbook localhost.yml -e "hostname=my-machine" -K
```

## Key Files

- `ansible.cfg` - Runtime configuration
- `template.yml` - Template configuration (primary)
- `kvm_setup.yml` - Proxmox VM setup
- `localhost.yml` - Local machine setup
- `roles/` - Reusable automation logic
- `inventory/hosts` - Host inventory

## Roles

- **common** - OS utilities and system configuration
- **template** - Ubuntu template setup
- **kvm_setup** - Proxmox KVM configuration

## Configuration

- Global vars: `group_vars/all.yml`
- Role vars: `roles/*/vars/main.yml`
- Runtime override: `-e "key=value"`

## Notes

- All playbooks are idempotent (safe to run multiple times)
- Secrets stored in system keyring (Linux: `secret-tool`, macOS: Keychain)
- No hardcoded credentials in code
