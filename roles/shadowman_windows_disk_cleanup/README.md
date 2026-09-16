# windows_manage_disk_cleanup

Reclaim disk space on Windows hosts by removing superseded Windows Update
component files and optionally clearing Windows event logs.

## Requirements

- Ansible >= 2.18
- `ansible.windows` collection

## Role Variables

| Variable | Type | Default | Description |
|---|---|---|---|
| `windows_manage_disk_cleanup_windows_update_files` | bool | `false` | Remove superseded Windows Update component files via DISM `/StartComponentCleanup` |
| `windows_manage_disk_cleanup_windows_update_reset` | bool | `false` | Also remove files needed to uninstall updates (DISM `/ResetBase`, irreversible) |
| `windows_manage_disk_cleanup_event_logs` | bool | `false` | Clear all Windows event log channels |

All actions default to `false`, so running the role with no variables set makes
no changes; enable only the cleanup steps you want.

## Example Playbook

```yaml
- name: Clean up disk space
  hosts: windows
  roles:
    - role: infra.windows_ops.windows_manage_disk_cleanup
      vars:
        windows_manage_disk_cleanup_windows_update_files: true
        windows_manage_disk_cleanup_windows_update_reset: false
        windows_manage_disk_cleanup_event_logs: true
```

## Notes

- **DISM component cleanup** is performed with `ansible.windows.win_command`.
  It is a maintenance action with no queryable "already clean" state, so the
  task always reports `changed` when it runs.
- **Event log clearing** uses `ansible.windows.win_powershell`. No native
  Ansible module can enumerate and clear every Windows event log channel, so
  PowerShell (`EventLogSession`) is used for this step; the task honours check
  mode and only reports `changed` when logs are actually cleared.

## License

GPL-3.0-or-later
