<!-- This was created with Claude Code -->

shadowman_scan_systems
======================

An Ansible role for shadowman scan systems.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **scan_use_checksum**: Check mode or validation flag
  - Default: `False`

* **scan_use_recursive**: Configuration parameter for shadowman_scan_systems
  - Default: `False`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_scan_systems
      vars:
        scan_use_checksum: <value>
        scan_use_recursive: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
