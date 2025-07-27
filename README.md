
# ansible-kubernetes-cli-tools

Ansible playbook to automate the installation of popular Kubernetes CLI tools:

- **helm**
- **kubectx**
- **kubens**
- **stern**

## Overview

This playbook downloads, extracts, and installs the above tools to your system, handling all necessary setup and cleanup steps. It is designed for use on Linux systems and can be easily extended for other tools.

## Structure

- `main.yaml`: Entry point for the playbook.
- `setup/`: Contains the main role and its tasks.
  - `defaults/main.yaml`: Default variables for the setup role.
  - `tasks/`:
    - `main.yaml`: Orchestrates the setup steps.
    - `download_files.yaml`: Downloads release archives and binaries.
    - `extract_files.yaml`: Extracts downloaded archives.
    - `copy_files.yaml`: Copies binaries to the install path.
    - `setup_temporary_folder.yaml`: Prepares a temporary working directory.
    - `cleanup.yaml`: Cleans up temporary files and folders.
    - `post_install.yaml`: (Optional) Post-installation steps.

## Usage

1. Clone this repository.
2. Adjust variables in `setup/defaults/main.yaml` as needed (e.g., install path, URLs).
3. Run the playbook:

   ```bash
   ansible-playbook main.yaml
   ```

## Customization

You can add or remove tools by editing the relevant task files in `setup/tasks/` and updating variables in `setup/defaults/main.yaml`.

---
Maintained by rhattox-ansible.
