# Ansible Playbook: RHEL - Patch Management

This Ansible playbook is designed to install patches and updates across Red Hat Enterprise Linux (RHEL) systems. It dynamically adjusts to RHEL versions 7, 8, and 9 and configures repositories, installs necessary packages, and applies updates.

## Configuration

The playbook uses variables such as `survey_hostname` or `survey_hosts` to target hosts for patch management. Ensure your Job Template in the Ansible Controller is handling these variables.

## Tasks

- **Dynamic Repository Management**: Enables appropriate repositories based on the RHEL version detected on the target machine.
- **Prerequisite Installation**: Installs necessary utilities like `yum-utils`.
- **Selective Package Updates**: Supports excluding specific packages from updates and can re-include them later if needed.
- **EPEL Updates**: Handles updates for packages from the EPEL repository.
- **Cleanup Operations**: Removes unused dependencies.
- **System Reboot Management**: Checks if a reboot is necessary after updates and performs it if required.

## Usage
Normally used as a scheduled job template in the Ansible Controller.

## Extra Variables
 - **survey_hostname** or **survey_hosts** (Required): Specifies the target hosts for patching.
 - **exclude_packages** (Optional): List of packages to exclude from updates.