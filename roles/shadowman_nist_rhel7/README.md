<!-- This was created with Claude Code -->

shadowman_nist_rhel7
====================

An Ansible role for shadowman nist rhel7.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **var_password_pam_unix_remember**: Configuration parameter for ansible.builtin.replace task
  - Default: `5`

* **var_accounts_passwords_pam_faillock_deny**: Password or authentication credential
  - Default: `3`

* **var_accounts_passwords_pam_faillock_fail_interval**: Password or authentication credential
  - Default: `900`

* **var_accounts_passwords_pam_faillock_unlock_time**: Password or authentication credential
  - Default: `0`

* **var_password_pam_dcredit**: Password or authentication credential
  - Default: `-1`

* **var_password_pam_difok**: Password or authentication credential
  - Default: `4`

* **var_password_pam_lcredit**: Password or authentication credential
  - Default: `-1`

* **var_password_pam_maxclassrepeat**: Password or authentication credential
  - Default: `4`

* **var_password_pam_maxrepeat**: Password or authentication credential
  - Default: `3`

* **var_password_pam_minlen**: Password or authentication credential
  - Default: `12`

* **var_password_pam_ocredit**: Password or authentication credential
  - Default: `-1`

* **var_password_pam_ucredit**: Password or authentication credential
  - Default: `-1`

* **var_accounts_password_minlen_login_defs**: Password or authentication credential
  - Default: `12`

* **var_accounts_max_concurrent_login_sessions**: Configuration parameter for ansible.builtin.replace task
  - Default: `10`

* **var_accounts_user_umask**: Configuration parameter for ansible.builtin.replace task
  - Default: `027`

* **var_auditd_flush**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `incremental_async`

* **sysctl_net_ipv6_conf_all_accept_ra_value**: Variable used in: net.ipv6.conf.all.accept_ra
  - Default: `0`

* **sysctl_net_ipv6_conf_all_accept_redirects_value**: Variable used in: net.ipv6.conf.all.accept_redirects
  - Default: `0`

* **sysctl_net_ipv6_conf_all_accept_source_route_value**: Variable used in: net.ipv6.conf.all.accept_source_route
  - Default: `0`

* **sysctl_net_ipv6_conf_default_accept_ra_value**: Variable used in: net.ipv6.conf.default.accept_ra
  - Default: `0`

* **sysctl_net_ipv6_conf_default_accept_redirects_value**: Variable used in: net.ipv6.conf.default.accept_redirects
  - Default: `0`

* **sysctl_net_ipv6_conf_default_accept_source_route_value**: Variable used in: net.ipv6.conf.default.accept_source_route
  - Default: `0`

* **sysctl_net_ipv4_conf_all_accept_redirects_value**: Variable used in: net.ipv4.conf.all.accept_redirects
  - Default: `0`

* **sysctl_net_ipv4_conf_all_accept_source_route_value**: Variable used in: net.ipv4.conf.all.accept_source_route
  - Default: `0`

* **sysctl_net_ipv4_conf_all_log_martians_value**: Variable used in: net.ipv4.conf.all.log_martians
  - Default: `1`

* **sysctl_net_ipv4_conf_all_rp_filter_value**: Variable used in: net.ipv4.conf.all.rp_filter
  - Default: `1`

* **sysctl_net_ipv4_conf_all_secure_redirects_value**: Variable used in: net.ipv4.conf.all.secure_redirects
  - Default: `0`

* **sysctl_net_ipv4_conf_default_accept_redirects_value**: Variable used in: net.ipv4.conf.default.accept_redirects
  - Default: `0`

* **sysctl_net_ipv4_conf_default_accept_source_route_value**: Variable used in: net.ipv4.conf.default.accept_source_route
  - Default: `0`

* **sysctl_net_ipv4_conf_default_log_martians_value**: Variable used in: net.ipv4.conf.default.log_martians
  - Default: `1`

* **sysctl_net_ipv4_conf_default_rp_filter_value**: Variable used in: net.ipv4.conf.default.rp_filter
  - Default: `1`

* **sysctl_net_ipv4_conf_default_secure_redirects_value**: Variable used in: net.ipv4.conf.default.secure_redirects
  - Default: `0`

* **sysctl_net_ipv4_icmp_echo_ignore_broadcasts_value**: Variable used in: net.ipv4.icmp_echo_ignore_broadcasts
  - Default: `1`

* **sysctl_net_ipv4_icmp_ignore_bogus_error_responses_value**: Variable used in: net.ipv4.icmp_ignore_bogus_error_responses
  - Default: `1`

* **sysctl_net_ipv4_tcp_syncookies_value**: Variable used in: net.ipv4.tcp_syncookies
  - Default: `1`

* **var_selinux_policy_name**: Resource name
  - Default: `targeted`

* **var_selinux_state**: Desired state (present, absent, started, stopped, etc.)
  - Default: `enforcing`

* **sshd_idle_timeout_value**: Timeout duration in seconds
  - Default: `600`

* **sshd_approved_ciphers**: IP address
  - Default: `aes128-ctr,aes192-ctr,aes256-ctr,aes128-cbc,3des-cbc,aes192-cbc,aes256-cbc,rijndael-cbc@lysator.liu.se`

* **sshd_approved_macs**: Application name or identifier
  - Default: `hmac-sha2-512,hmac-sha2-256,hmac-sha1,hmac-sha1-etm@openssh.com,hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_nist_rhel7
      vars:
        var_password_pam_unix_remember: <value>
        var_accounts_passwords_pam_faillock_deny: <value>
        var_accounts_passwords_pam_faillock_fail_interval: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
