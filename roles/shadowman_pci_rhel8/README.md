<!-- This was created with Claude Code -->

shadowman_pci_rhel8
===================

An Ansible role for shadowman pci rhel8.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **var_system_crypto_policy**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `DEFAULT`

* **inactivity_timeout_value**: Timeout duration in seconds
  - Default: `900`

* **var_password_pam_unix_remember**: Configuration parameter for ansible.builtin.replace task
  - Default: `4`

* **var_accounts_passwords_pam_faillock_deny**: Password or authentication credential
  - Default: `6`

* **var_accounts_passwords_pam_faillock_unlock_time**: Password or authentication credential
  - Default: `1800`

* **var_password_pam_dcredit**: Password or authentication credential
  - Default: `-1`

* **var_password_pam_lcredit**: Password or authentication credential
  - Default: `-1`

* **var_password_pam_minlen**: Password or authentication credential
  - Default: `7`

* **var_password_pam_ucredit**: Password or authentication credential
  - Default: `-1`

* **var_password_hashing_algorithm**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `SHA512`

* **var_smartcard_drivers**: Variable used in: Configure opensc Smart Card Drivers
  - Default: `cac`

* **var_account_disable_post_pw_expiration**: Disable feature flag
  - Default: `90`

* **var_accounts_maximum_age_login_defs**: Numeric count or quantity
  - Default: `90`

* **var_auditd_action_mail_acct**: Variable used in: Configure auditd mail_acct Action on Low Disk Space
  - Default: `root`

* **var_auditd_admin_space_left_action**: Variable used in: Configure auditd admin_space_left Action on Low Disk Space
  - Default: `single`

* **var_auditd_max_log_file**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `6`

* **var_auditd_max_log_file_action**: Variable used in: Configure auditd max_log_file_action Upon Reaching Maximum Log Size
  - Default: `rotate`

* **var_auditd_num_logs**: Variable used in: Configure auditd Number of Logs Retained
  - Default: `5`

* **var_auditd_space_left_action**: Variable used in: Configure auditd space_left Action on Low Disk Space
  - Default: `email`

* **var_multiple_time_servers**: IP address
  - Default: `0.rhel.pool.ntp.org,1.rhel.pool.ntp.org,2.rhel.pool.ntp.org,3.rhel.pool.ntp.org`

* **sshd_idle_timeout_value**: Timeout duration in seconds
  - Default: `900`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_pci_rhel8
      vars:
        var_system_crypto_policy: <value>
        inactivity_timeout_value: <value>
        var_password_pam_unix_remember: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
