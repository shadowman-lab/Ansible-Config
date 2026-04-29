<!-- This was created with Claude Code -->

shadowman_cert_check
====================

An Ansible role for shadowman cert check.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **certificate_port**: Variable used in: Get the cert from a port
  - Default: `443`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_cert_check
      vars:
        certificate_port: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
