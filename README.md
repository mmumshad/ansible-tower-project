# Ansible Azure Roles and Playbooks

This repository contains Ansible Azure Roles and Playbooks.

Must define the following variables:

```

vm_name:            # eg: windows-vm-test
vm_image:           # eg: WIN_2016
os_type:            # eg: Windows

# General
resource_group:
location:           # eg: eastus2

# VM Provisioning
vm_size:            # eg: Standard_A2_v2
admin_username:
admin_password:     # Required for Windows

# If Linux
ssh_password_enabled: false
ssh_public_keys:
  - path:
    key_data:

# Network
virtual_network_name:   # eg: VN-NET1
subnet_name:            # eg: SN-NET1
address_prefixes:
  - 10.0.0.0/24
# Storage
storage_account_name:   
managed_disk_type:      # eg: Standard_LRS
os_disk_size_gb:        # eg: 32 . Consider the minimum size for Windows.

# Diagnostics Storage Accounts
diagnostic_storage_account_name:
diagnostic_storage_account_id:    # eg: /subscriptions/f5bd840e-xxxx-xxxx-xxxx-xxxxxxxxxxx/resourceGroups/xx-xxxxxx/providers/Microsoft.Storage/storageAccounts/xx-xxxx

# VM Image
vm_image: RHEL_7 # Picks from the images listed in azure-provision-vm-linux/defaults/main.yaml

# Default VM Tags. Override in the playbook.
tags:
  purpose: vm-gp

```
