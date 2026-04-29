<!-- This was created with Claude Code -->

shadowman_idm_user
==================

An Ansible role for shadowman idm user.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **idm_group_names**: Resource name
  - Default: `{{ group_name.split(',') }}`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_idm_user
      vars:
        idm_group_names: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
