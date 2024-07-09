build_report_windows
========

Installs Apache and creates a report based on facts from Windows services and packages modules. Utilize var "detailedreport=false" if you do not need packages or services information. Use in combination with win_scan_packages and win_scan_services modules included in the collection


Requirements
------------

Must run on Apache server

Role Variables / Configuration
--------------

N/A

Dependencies
------------

N/A

Example Playbook
----------------

The role can be used to create an html report on any number of Linux hosts using any number of Windows servers about their services and packages installed. Added in a boolean var usesingletemplate if running into issues with jinja not adding in the package/services facts.


```
---
- name: Create Windows Report
  hosts: all
  tasks:

    - name: "Scan packages (Windows)"
      shadowman.reports.win_scan_packages:
      when: ansible_os_family == "Windows"

    - name: "Scan services (Windows)"
      shadowman.reports.win_scan_services:
      when: ansible_os_family == "Windows"

    - name: Build the report
      ansible.builtin.include_role:
        name: shadowman.reports.build_report_windows
        apply:
          delegate_to: report.shadowman.dev
          run_once: true
      
```
