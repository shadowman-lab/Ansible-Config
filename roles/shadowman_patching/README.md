<!-- This was created with Claude Code -->

shadowman_patching
==================

An Ansible role for shadowman patching.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **acceptlist**: List of items

* **rejectlist**: List of items

* **categories**: Category or classification
  - Default: `*`

* **exclude_packages**: Items to exclude from operation
  - Default: `{{ exclude.split(',') }}`

* **exclude**: Items to exclude from operation

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_patching
      vars:
        acceptlist: <value>
        rejectlist: <value>
        categories: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
