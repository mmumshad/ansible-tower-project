# Ansible Role: azure-backup

**Research:** No option available with the default `azure_rm_virtualmachine` ansible module to enbale backup. No ansible modules found that can support this natively.

**Pending**: Look into backup agent installation on the VM

Also look at ARM Template Creations with Backup enabled.

Azure CLI:

```
az backup protection enable-for-vm \
    --resource-group myResourceGroup \
    --vault-name myRecoveryServicesVault \
    --vm $(az vm show -g VMResourceGroup -n MyVm --query id | tr -d '"') \
    --policy-name DefaultPolicy
    ```

Azure Rest API: https://docs.microsoft.com/en-us/rest/api/backup/protecteditems/createorupdate#enable_protection_on_azure_iaasvm

 **Required Inputs**:
  - *backup_recovery_vault:* Recovery Services Vault name
  - *backup_policy_name:* Backup Policy name
