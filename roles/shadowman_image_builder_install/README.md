<!-- This was created with Claude Code -->

shadowman_image_builder_install
===============================

An Ansible role for shadowman image builder install.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **rhsatellite**: Variable used in: Block for Sat Install
  - Default: `True`

* **sat_host**: Target host or hostname
  - Default: `sat6.shadowman.dev`

* **sat_organization**: Organization name or identifier
  - Default: `Shadow_Man`

* **sat_environment**: Environment name or configuration
  - Default: `Development`

* **sat_contentview**: Content data
  - Default: `Everything_Red_Hat`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_image_builder_install
      vars:
        rhsatellite: <value>
        sat_host: <value>
        sat_organization: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
