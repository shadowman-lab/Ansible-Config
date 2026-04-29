<!-- This was created with Claude Code -->

shadowman_snapshot_restore
==========================

An Ansible role for shadowman snapshot restore.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **description**: Variable used in: {{ inventory_hostname }}
  - Default: `pre_patch`

* **snap_name**: Variable used in: {{ inventory_hostname }}
  - Default: `pre_patch_snapshot`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_snapshot_restore
      vars:
        description: <value>
        snap_name: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
