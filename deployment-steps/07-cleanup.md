# 07 - Cleanup

## Purpose

The final step of the lab is understanding how to clean up Azure resources when the project is finished.

Cleanup is important because Azure resources can continue generating costs if they are left running.

---

## Cleanup Strategy

All lab resources were deployed inside one dedicated resource group:

| Resource Group |
|---|
| `rg-enterprise-lab` |

Because the resources are grouped together, the entire lab can be removed by deleting the resource group.

---

## Resources That Would Be Deleted

Deleting the resource group removes the lab resources, including:

- Virtual machines
- Managed disks
- Network interfaces
- Public IP addresses
- Virtual network
- Subnets
- Network Security Groups
- Log Analytics Workspace
- Alert rules
- Recovery Services Vault
- Backup configuration

---

## Important Backup Note

Before deleting a Recovery Services Vault, backup protection and backup data may need to be stopped or removed.

Azure may prevent vault deletion until protected items, recovery points, or soft-delete settings are handled.

---

## Cleanup Steps

To clean up the lab:

1. Go to the Azure Portal
2. Open **Resource groups**
3. Select `rg-enterprise-lab`
4. Review the resources inside the group
5. Stop backup protection if needed
6. Delete protected backup items if required
7. Delete the resource group
8. Confirm deletion by typing the resource group name

---

## Cost Control

During the lab, virtual machines should be stopped when not in use to reduce cost.

Recommended cost-control actions:

- Stop VMs when finished testing
- Delete unused public IP addresses
- Remove unused disks
- Delete old recovery points when no longer needed
- Delete the entire resource group after the lab is complete

---

## Result

A cleanup plan was documented to prevent unnecessary Azure charges and to safely remove the lab environment when it is no longer needed.
