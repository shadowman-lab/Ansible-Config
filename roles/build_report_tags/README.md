build_report_tags
========

Installs Apache and creates a report based on tags from RHV, VMWare, or Azure.

Requirements
------------

Must run on Apache server

Role Variables / Configuration
--------------

Must register rhv results as rhv_info, azure results as azure_info, and vmware results as vmware_info. Set var sendemailreport to false if not also sending the report via e-mail

Dependencies
------------

N/A

Example Playbook
----------------

The role can be used to create an html report on the tags from Azure, RHV, and VMWare


```
- name: Build Tags Report
  hosts: localhost
  gather_facts: false

  tasks:

    - name: Get VMWare tag info
      community.vmware.vmware_vm_info:
        validate_certs: false
        show_tag: true
        vm_type: "vm"
      register: vmware_info

    - name: Get Azure VM Info
      azure.azcollection.azure_rm_virtualmachine_info:
        tags:
          - owner
      register: azure_info

    - name: Block for RHV
      block:
      - name: Login to RHV
        redhat.rhv.ovirt_auth:
          hostname: "{{ rhvm_fqdn }}"
          username: "{{ rhvm_user }}"
          password: "{{ rhvm_password }}"
          ca_file: "{{ rhvm_cafile | default(omit) }}"
          insecure: "{{ rhvm_insecure | default(true) }}"  

      - name: Get RHV VM info
        redhat.rhv.ovirt_vm_info:
          auth: "{{ ovirt_auth }}"
          follow:
            - tags
        register: rhv_info

      always:
        - name: Logout from RHV
          redhat.rhv.ovirt_auth:
            state: absent
            ovirt_auth: "{{ ovirt_auth }}"

    - name: Build the report
      ansible.builtin.include_role:
        name: shadowman.reports.build_report_tags
        apply:
          delegate_to: report.shadowman.dev
          run_once: true     
```
