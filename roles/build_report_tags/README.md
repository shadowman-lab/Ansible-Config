build_report_linux_patch
========

Installs Apache and creates a report based on facts from RHEL patching. Could be expanded for patching other Linux distros but would require reviewing json output

Requirements
------------

Must run on Apache server

Role Variables / Configuration
--------------

Must register yum results as patchingresult and dnf results as patchingresultdnf. Set var sendemailreport to false if not also sending the report via e-mail

Dependencies
------------

N/A

Example Playbook
----------------

The role can be used to create an html report on any number of RHEL hosts using any number of RHEL servers about their patching results(yum and dnf)


```
---
- name: Patch RHEL Servers
  hosts: all

  tasks:
  
  - name: upgrade all packages (yum)
    ansible.builtin.yum:
      name: '*'
      state: latest
    when: ansible_pkg_mgr == "yum"
    register: patchingresult
  
  - name: upgrade all packages (dnf)
    ansible.builtin.dnf:
      name: '*'
      state: latest
    when: ansible_pkg_mgr == "dnf"
    register: patchingresultdnf
  
  - name: Build the report
    ansible.builtin.include_role:
      name: shadowman.reports.build_report_linux_patch
      apply:
        delegate_to: report.shadowman.dev
        run_once: true     
```
