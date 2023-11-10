build_report_azure
========

Installs Apache and creates a report based on facts from Azure.

Requirements
------------

Must deploy to Apache server

Role Variables / Configuration
--------------

N/A

Dependencies
------------

N/A

Example Playbook
----------------

The role can be used to create an html report on Azure statistics onto an apache server.


```
---
- name: Create Cloud Report
  hosts: localhost
  tasks:

  - name: Get list of all regions
    azure.azcollection.azure_rm_resource_info:
      url: "/locations"
      api_version: "2020-01-01"
    register: all_regions

  - name: Get all networks
    azure.azcollection.azure_rm_virtualnetwork_info:
    register: azure_networks

  - name: Get all vms
    azure.azcollection.azure_rm_virtualmachine_info:
    register: azure_vms

  - name: Get facts for network interfaces
    azure.azcollection.azure_rm_networkinterface_info:
    register: network_interfaces

  - name: Build the report
    ansible.builtin.include_role:
      name: shadowman.reports.build_report_azure
      apply:
        delegate_to: report.shadowman.dev
        run_once: true      
```
