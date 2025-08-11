# proxmox-ubuntu-server-raw

Project with Packer and Ansible scripts to create an Ubuntu template on Proxmox from an ISO file with the bare minimum packages and updates.

### Overview

This project can be used in two main scenarios:

1. **Proxmox VM (Recommended)**:

    If your VM is created via **Packer** (and optionally Terraform), most Ansible playbooks will be executed automatically as part of the provisioning process. You do not need to run them manually.

1. **Manual Setup (VirtualBox or Custom VM)**:

    If you created your VM manually (e.g., in VirtualBox), you need to run the Ansible playbooks yourself.

### Installation and Setup

### 1. Prepare the Environment

**For both Proxmox VMs and VirtualBox:**

Open a terminal and execute the following steps:

1. Update package lists and upgrade installed packages
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

1. Install Git (if not already installed)
    ```bash
    sudo apt install -y git
    ```

1. Create a Git directory and navigate to it
    ```bash
    mkdir -p ~/git && cd ~/git
    ```

1. Clone the repository and initialize submodules
    ```bash
    git clone --recurse-submodules https://github.com/lsampaioweb/proxmox-ubuntu-server-raw.git && cd proxmox-ubuntu-server-raw
    ```

1. If the repository is already cloned, update submodules
    ```bash
    git submodule update --init --recursive
    ```

### 2. Deploy the Template

Choose one of the following methods:

- **[Packer](packer/README.md "Packer")** (Recommended for Proxmox) – Automated deployment if your Proxmox cluster is operational.
- **[Ansible](ansible/README.md "Ansible")** – Manual configuration for VirtualBox VMs when Packer isn't available.

#
### Links:

[Links](links.md "Links")

### License:

[MIT](LICENSE "MIT License")

### Created by:

1. Luciano Sampaio.
