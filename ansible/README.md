# proxmox-ubuntu-server-raw
Project with Ansible scripts to create an Ubuntu template on Proxmox from an ISO file with the bare minimum packages and updates.

### Manual Usage:

1. Change to the ansible directory.
    ```bash
    cd ansible
    ```

1. Run the playbooks as needed:

    1. Virtualbox VM:

        Install and setup application.
        ```bash
        ansible-playbook localhost.yml
        ```

    1. Proxmox VM:

        Install and setup application.
        ```bash
        ansible-playbook template.yml -e "password_id=ubuntu-24-04-server-raw"
        ```

        Setup VM settings on Proxmox.
        ```bash
        ansible-playbook kvm_setup.yml -e "node=edge-pve-01 vm_name=ubuntu-24-04-server-raw cpu_type=x86-64-v2-AES hotplug=disk,network,cpu"
        ```

#
### Created by:

1. Luciano Sampaio.
