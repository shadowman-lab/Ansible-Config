Windows Server 2016 DISA STIG
=========


Configure a Windows Server 2016 system to be DISA STIG compliant. All findings will be audited by default. Non-disruptive CAT I, CAT II, and CAT III findings will be corrected by default.

This role is based on Windows Server 2016 DISA STIG: [Version 2, Rel 1 released on November 13, 2020](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_MS_Windows_Server_2016_V2R1_STIG.zip).

Requirements
------------

Windows Server 2016 - Other versions are not supported.

Dependencies
------------

The following packages must be installed on the controlling host/host where ansible is executed:

- passlib (or python2-passlib, if using python2)
- python-lxml
- python-xmltodict
- python-jmespath
- pywinrm

Package 'python-xmltodict' is required if you enable the OpenSCAP tool installation and run a report. Packages python(2)-passlib and python-jmespath are required for tasks with custom filters or modules. These are all required on the controller host that executes Ansible.

Role Variables
--------------

Please see the Ansible docs for understanding [variable precedence](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#variable-precedence-where-should-i-put-a-variable) to tailor for your needs. 

| Name                     | Default Value       | Description                   |
|--------------------------|-----------------------------------------------------|----------------------|
| `win2016stig_cat1_patch` | `yes` see defaults/main.yml](./defaults/main.yml)   | Correct CAT I findings        |
| `win2016stig_cat2_patch` | `yes`  see defaults/main.yml](./defaults/main.yml)  | Correct CAT II findings       |
| `win2016stig_cat3_patch` | `yes`  see defaults/main.yml](./defaults/main.yml)  | Correct CAT III findings      |
| `wn16_##_######`         | [see defaults/main.yml](./defaults/main.yml)        | Individual variables to enable/disable each STIG ID. |

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: win-2k16-stig
           when:
                - ansible_os_family == 'Windows'
                - ansible_distribution | regex_search('(Server 2016)')
