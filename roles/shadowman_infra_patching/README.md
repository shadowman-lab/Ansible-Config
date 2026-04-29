<!-- This was created with Claude Code -->

shadowman_infra_patching
========================

An Ansible role for shadowman infra patching.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **exclude_packages**: Variable used in: *
  - Default: `{{ exclude.split(',') }}`

* **exclude**: Variable used in: *

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_infra_patching
      vars:
        exclude_packages: <value>
        exclude: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
