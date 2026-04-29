<!-- This was created with Claude Code -->

shadowman_compliance_playbook_create
====================================

An Ansible role for shadowman compliance playbook create.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **file_path**: File system path
  - Default: `/var/www/html/openscap`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_compliance_playbook_create
      vars:
        file_path: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
