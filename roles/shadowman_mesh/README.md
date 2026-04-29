<!-- This was created with Claude Code -->

shadowman_mesh
==============

An Ansible role for shadowman mesh.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **mesh_target**: Variable used in: Show mesh status
  - Default: `rhel8.shadowman.dev`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_mesh
      vars:
        mesh_target: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
