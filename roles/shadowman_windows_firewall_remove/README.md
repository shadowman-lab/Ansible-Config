<!-- This was created with Claude Code -->

shadowman_windows_firewall_remove
=================================

An Ansible role for shadowman windows firewall remove.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **mattermost_url**: Variable used in: Send notification message via Mattermost
  - Default: `https://cicd.shadowman.dev:8065`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_windows_firewall_remove
      vars:
        mattermost_url: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
