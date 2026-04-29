<!-- This was created with Claude Code -->

shadowman_aap_roi
=================

An Ansible role for shadowman aap roi.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **manual_time_per_job**: this is in seconds, 300 is 5 minutes
  - Default: `300`

* **usesingletemplate**: use if jinja issues happen
  - Default: `False`

* **automated_process_cost**: if the below says 10, its $10 per hour to run this automation
  - Default: `10`

* **manual_cost_per_hour**: this is the cost of an engineer to do the eqvuialent of automation (manually configure something)
  - Default: `30.0`

* **manual_cost_per_hour_to_automate**: this is the cost of an engineer to create automation, e.g. create an Ansible Playbook and test it
  - Default: `80`

* **hours_to_create_automation**: this is amount of time in hours to develop automation for this use case
  - Default: `1`

* **days_per_year_fte**: days per year of FTE (full time engineer), default is 52 weeks a year * 5 days a week or 260
  - Default: `260`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_aap_roi
      vars:
        manual_time_per_job: <value>
        usesingletemplate: <value>
        automated_process_cost: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
