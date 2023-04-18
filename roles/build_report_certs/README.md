build_report_certs
========

Installs Apache and creates a report based on certificates on a specified port

Requirements
------------

Must run on Apache server

Role Variables / Configuration
--------------

Must register facts for each host expire_days, issuer, expiration, expired. Set var sendemailreport to false if not also sending the report via e-mail

Dependencies
------------

N/A

Example Playbook
----------------

The role can be used to create an html report on any number of RHEL hosts using any number of servers about their certificate results


```
---
- name: Check Certificates on port
  hosts: all

  tasks:
  
  - name: Get the cert from a port
    community.crypto.get_certificate:
      host: "{{ inventory_hostname }}"
      port: "{{ certificate_port }}"
    delegate_to: localhost
    register: cert
    no_log: true
  
  - name: Set facts for report
    ansible.builtin.set_fact:
      expire_days: "{{ ((cert.not_after | to_datetime('%Y%m%d%H%M%SZ')) - (ansible_date_time.iso8601 | to_datetime('%Y-%m-%dT%H:%M:%SZ'))).days }}"
      issuer: "{{ cert.issuer }}"
      expiration: "{{ cert.not_after | to_datetime('%Y%m%d%H%M%SZ') }}"
      expired: "{{ cert.expired }}"

  - name: Build the report
    ansible.builtin.include_role:
      name: build_report_certs
      apply:
        delegate_to: report.shadowman.dev
        run_once: true
```
