# 06 - Backup

## Purpose

Azure Backup was configured to protect the Windows Server virtual machine in the lab.

Backup is important because administrators need a way to recover virtual machines after accidental deletion, corruption, failed updates, or other issues.

---

## Backup Components Used

| Component | Purpose |
|---|---|
| Recovery Services Vault | Stores backup configuration and recovery points |
| Backup Policy | Defines backup behavior and retention |
| Protected VM | The virtual machine selected for backup |
| Recovery Point | A restore point created by Azure Backup |

---

## Backup Configuration

| Setting | Value |
|---|---|
| Recovery Services Vault | `rsv-enterprise-lab` |
| Protected VM | `vm-win-server01` |
| Backup Type | Azure VM Backup |
| Backup Policy | Enhanced policy |
| Backup Status | Succeeded |
| Backup Pre-Check | Passed |

---

## What Was Protected

The Windows Server VM was selected for backup protection.

This means Azure Backup can create recovery points that allow the VM to be restored if needed.

---

## Why This Matters

Backup is a core responsibility for system administrators and cloud administrators.

This lab demonstrates understanding of:

- Recovery Services Vaults
- VM backup protection
- Backup policies
- Recovery points
- Restore readiness
- Basic disaster recovery planning

---

## Recovery Point

A recovery point was successfully created for the protected virtual machine.

The successful backup status confirms that the VM backup configuration is working.

---

## Evidence

The screenshot below shows the successful Azure Backup status and recovery point.

![Backup Success](../screenshots/backup/backup-success.png)

---

## Result

Azure Backup was successfully configured for the Windows Server VM, and a recovery point was created.
