<!-- This was created with Claude Code -->

shadowman_cis_rhel7
===================

An Ansible role for shadowman cis rhel7.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **var_sudo_logfile**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `/var/log/sudo.log`

* **login_banner_text**: Variable used in: Modify the System Login Banner - ensure correct banner
  - Default: `^\-\-[\s\n]+WARNING[\s\n]+\-\-[\s\n]+This[\s\n]+system[\s\n]+is[\s\n]+for[\s\n]+the[\s\n]+use[\s\n]+of[\s\n]+authorized[\s\n]+users[\s\n]+only\.[\s\n]+Individuals[\s\n]+using[\s\n]+this[\s\n]+computer[\s\n]+system[\s\n]+without[\s\n]+authority[\s\n]+or[\s\n]+in[\s\n]+excess[\s\n]+of[\s\n]+their[\s\n]+authority[\s\n]+are[\s\n]+subject[\s\n]+to[\s\n]+having[\s\n]+all[\s\n]+their[\s\n]+activities[\s\n]+on[\s\n]+this[\s\n]+system[\s\n]+monitored[\s\n]+and[\s\n]+recorded[\s\n]+by[\s\n]+system[\s\n]+personnel\.[\s\n]+Anyone[\s\n]+using[\s\n]+this[\s\n]+system[\s\n]+expressly[\s\n]+consents[\s\n]+to[\s\n]+such[\s\n]+monitoring[\s\n]+and[\s\n]+is[\s\n]+advised[\s\n]+that[\s\n]+if[\s\n]+such[\s\n]+monitoring[\s\n]+reveals[\s\n]+possible[\s\n]+evidence[\s\n]+of[\s\n]+criminal[\s\n]+activity[\s\n]+system[\s\n]+personal[\s\n]+may[\s\n]+provide[\s\n]+the[\s\n]+evidence[\s\n]+of[\s\n]+such[\s\n]+monitoring[\s\n]+to[\s\n]+law[\s\n]+enforcement[\s\n]+officials\.$`

* **var_password_pam_remember**: Variable used in: password-auth
  - Default: `5`

* **var_password_pam_remember_control_flag**: Variable used in: password-auth
  - Default: `required`

* **var_password_pam_minclass**: Password or authentication credential
  - Default: `4`

* **var_password_pam_minlen**: Password or authentication credential
  - Default: `14`

* **var_account_disable_post_pw_expiration**: Disable feature flag
  - Default: `30`

* **var_accounts_maximum_age_login_defs**: Numeric count or quantity
  - Default: `365`

* **var_accounts_minimum_age_login_defs**: Numeric count or quantity
  - Default: `1`

* **var_accounts_password_warn_age_login_defs**: Password or authentication credential
  - Default: `7`

* **var_accounts_tmout**: Numeric count or quantity
  - Default: `900`

* **var_accounts_user_umask**: Configuration parameter for ansible.builtin.replace task
  - Default: `027`

* **var_auditd_action_mail_acct**: Variable used in: Configure auditd mail_acct Action on Low Disk Space
  - Default: `root`

* **var_auditd_admin_space_left_action**: Variable used in: Configure auditd admin_space_left Action on Low Disk Space
  - Default: `halt`

* **var_auditd_max_log_file**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `6`

* **var_auditd_max_log_file_action**: Variable used in: Configure auditd max_log_file_action Upon Reaching Maximum Log Size
  - Default: `keep_logs`

* **var_auditd_space_left_action**: Variable used in: Configure auditd space_left Action on Low Disk Space
  - Default: `email`

* **sysctl_net_ipv6_conf_all_accept_ra_value**: Variable used in: net.ipv6.conf.all.accept_ra
  - Default: `0`

* **sysctl_net_ipv6_conf_all_accept_redirects_value**: Variable used in: net.ipv6.conf.all.accept_redirects
  - Default: `0`

* **sysctl_net_ipv6_conf_all_accept_source_route_value**: Variable used in: net.ipv6.conf.all.accept_source_route
  - Default: `0`

* **sysctl_net_ipv6_conf_all_forwarding_value**: Variable used in: net.ipv6.conf.all.forwarding
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

* **var_removable_partition**: Configuration parameter for ansible.builtin.lineinfile task
  - Default: `/dev/cdrom`

* **var_selinux_policy_name**: Resource name
  - Default: `targeted`

* **var_selinux_state**: Desired state (present, absent, started, stopped, etc.)
  - Default: `enforcing`

* **var_postfix_inet_interfaces**: Network interface configuration
  - Default: `loopback-only`

* **var_multiple_time_servers**: IP address
  - Default: `0.rhel.pool.ntp.org,1.rhel.pool.ntp.org,2.rhel.pool.ntp.org,3.rhel.pool.ntp.org`

* **sshd_idle_timeout_value**: Timeout duration in seconds
  - Default: `900`

* **var_sshd_set_keepalive**: Variable value
  - Default: `0`

* **sshd_max_auth_tries_value**: Value to set
  - Default: `4`

* **var_sshd_max_sessions**: Maximum value
  - Default: `10`

* **var_sshd_set_maxstartups**: Start operation flag
  - Default: `10:30:60`

* **sshd_approved_ciphers**: IP address
  - Default: `chacha20-poly1305@openssh.com,aes128-ctr,aes192-ctr,aes256-ctr,aes128-gcm@openssh.com,aes256-gcm@openssh.com,aes128-cbc,aes192-cbc,aes256-cbc,blowfish-cbc,cast128-cbc,3des-cbc`

* **sshd_approved_macs**: Application name or identifier
  - Default: `umac-64-etm@openssh.com,umac-128-etm@openssh.com,hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com,hmac-sha1-etm@openssh.com,umac-64@openssh.com,umac-128@openssh.com,hmac-sha2-256,hmac-sha2-512,hmac-sha1,hmac-sha1-etm@openssh.com`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_cis_rhel7
      vars:
        var_sudo_logfile: <value>
        login_banner_text: <value>
        var_password_pam_remember: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
