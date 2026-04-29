<!-- This was created with Claude Code -->

shadowman_run_scap
==================

An Ansible role for shadowman run scap.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **file_path**: Variable used in: Copy folders to reports host
  - Default: `/var/www/html/openscap`

* **email_from**: Email address
  - Default: `tower@shadowman.dev`

* **to_emails**: Email address
  - Default: `alex@shadowman.dev,tower@shadowman.dev`

* **email_to**: Email address
  - Default: `{{ to_emails.split(',') }}`

* **sendemailreport**: Network port number
  - Default: `True`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_run_scap
      vars:
        file_path: <value>
        email_from: <value>
        to_emails: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
