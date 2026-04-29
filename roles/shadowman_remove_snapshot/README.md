<!-- This was created with Claude Code -->

shadowman_remove_snapshot
=========================

An Ansible role for shadowman remove snapshot.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **datacenter**: Variable used in: Delete a snapshot
  - Default: `Default`

* **cluster**: Cluster name or identifier
  - Default: `Default`

* **vm_names**: Virtual machine name
  - Default: `{{ vm_name.split(',') }}`

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
    - role: shadowman_remove_snapshot
      vars:
        datacenter: <value>
        cluster: <value>
        vm_names: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
