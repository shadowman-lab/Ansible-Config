<!-- This was created with Claude Code -->

# Config Automation

This directory contains Ansible automation for config management and operations.

## Overview

The Config automation provides playbooks and roles for managing and configuring 
config infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [shadowman_aap_metrics](roles/shadowman_aap_metrics/README.md) | Role for shadowman aap metrics |
| [shadowman_aap_metrics_api](roles/shadowman_aap_metrics_api/README.md) | Role for shadowman aap metrics api |
| [shadowman_aap_roi](roles/shadowman_aap_roi/README.md) | Role for shadowman aap roi |
| [shadowman_active_directory](roles/shadowman_active_directory/README.md) | Role for shadowman active directory |
| [shadowman_ad_user_info](roles/shadowman_ad_user_info/README.md) | Role for shadowman ad user info |
| [shadowman_add_to_ad](roles/shadowman_add_to_ad/README.md) | Role for shadowman add to ad |
| [shadowman_add_to_idm](roles/shadowman_add_to_idm/README.md) | Role for shadowman add to idm |
| [shadowman_cert_check](roles/shadowman_cert_check/README.md) | Role for shadowman cert check |
| [shadowman_cis_rhel7](roles/shadowman_cis_rhel7/README.md) | Role for shadowman cis rhel7 |
| [shadowman_cis_rhel8](roles/shadowman_cis_rhel8/README.md) | Role for shadowman cis rhel8 |
| [shadowman_cis_windows_2016](roles/shadowman_cis_windows_2016/README.md) | Ansible role to apply Windows Server 2016 CIS Benchmark |
| [shadowman_compliance_playbook_create](roles/shadowman_compliance_playbook_create/README.md) | Role for shadowman compliance playbook create |
| [shadowman_compliance_scan](roles/shadowman_compliance_scan/README.md) | Role for shadowman compliance scan |
| [shadowman_create_snapshot](roles/shadowman_create_snapshot/README.md) | Role for shadowman create snapshot |
| [shadowman_esx_migrate_vms](roles/shadowman_esx_migrate_vms/README.md) | Role for shadowman esx migrate vms |
| [shadowman_esx_update](roles/shadowman_esx_update/README.md) | Role for shadowman esx update |
| [shadowman_gather_tags](roles/shadowman_gather_tags/README.md) | Role for shadowman gather tags |
| [shadowman_hashi_sshd_config](roles/shadowman_hashi_sshd_config/README.md) | Role for shadowman hashi sshd config |
| [shadowman_idm_user](roles/shadowman_idm_user/README.md) | Role for shadowman idm user |
| [shadowman_image_builder_cockpit_ssl](roles/shadowman_image_builder_cockpit_ssl/README.md) | Role for shadowman image builder cockpit ssl |
| [shadowman_image_builder_install](roles/shadowman_image_builder_install/README.md) | Role for shadowman image builder install |
| [shadowman_infra_patching](roles/shadowman_infra_patching/README.md) | Role for shadowman infra patching |
| [shadowman_kernel_cleanup](roles/shadowman_kernel_cleanup/README.md) | Role for shadowman kernel cleanup |
| [shadowman_linux_setup](roles/shadowman_linux_setup/README.md) | Role for shadowman linux setup |
| [shadowman_local_user_remove](roles/shadowman_local_user_remove/README.md) | Role for shadowman local user remove |
| [shadowman_mesh](roles/shadowman_mesh/README.md) | Role for shadowman mesh |
| [shadowman_nist_rhel7](roles/shadowman_nist_rhel7/README.md) | Role for shadowman nist rhel7 |
| [shadowman_nist_rhel8](roles/shadowman_nist_rhel8/README.md) | Role for shadowman nist rhel8 |
| [shadowman_patching](roles/shadowman_patching/README.md) | Role for shadowman patching |
| [shadowman_patching_async](roles/shadowman_patching_async/README.md) | Role for shadowman patching async |
| [shadowman_pci_rhel7](roles/shadowman_pci_rhel7/README.md) | Role for shadowman pci rhel7 |
| [shadowman_pci_rhel8](roles/shadowman_pci_rhel8/README.md) | Role for shadowman pci rhel8 |
| [shadowman_podman_cleanup](roles/shadowman_podman_cleanup/README.md) | Role for shadowman podman cleanup |
| [shadowman_podman_cleanup_edahub](roles/shadowman_podman_cleanup_edahub/README.md) | Role for shadowman podman cleanup edahub |
| [shadowman_reboot](roles/shadowman_reboot/README.md) | Role for shadowman reboot |
| [shadowman_register_insights](roles/shadowman_register_insights/README.md) | Role for shadowman register insights |
| [shadowman_remove_snapshot](roles/shadowman_remove_snapshot/README.md) | Role for shadowman remove snapshot |
| [shadowman_rhel_register](roles/shadowman_rhel_register/README.md) | Role for shadowman rhel register |
| [shadowman_rhel_template_seal](roles/shadowman_rhel_template_seal/README.md) | Role for shadowman rhel template seal |
| [shadowman_run_scap](roles/shadowman_run_scap/README.md) | Role for shadowman run scap |
| [shadowman_run_scap_windows](roles/shadowman_run_scap_windows/README.md) | Role for shadowman run scap windows |
| [shadowman_scan_systems](roles/shadowman_scan_systems/README.md) | Role for shadowman scan systems |
| [shadowman_schedule](roles/shadowman_schedule/README.md) | Role for shadowman schedule |
| [shadowman_schedule_cr](roles/shadowman_schedule_cr/README.md) | Role for shadowman schedule cr |
| [shadowman_snapshot_restore](roles/shadowman_snapshot_restore/README.md) | Role for shadowman snapshot restore |
| [shadowman_stig_windows_2016](roles/shadowman_stig_windows_2016/README.md) | Apply the DISA Windows Server 2016 STIG |
| [shadowman_tower_metrics](roles/shadowman_tower_metrics/README.md) | Role for shadowman tower metrics |
| [shadowman_vcenter_admin](roles/shadowman_vcenter_admin/README.md) | Role for shadowman vcenter admin |
| [shadowman_vmware_vm_info](roles/shadowman_vmware_vm_info/README.md) | Role for shadowman vmware vm info |
| [shadowman_windows_firewall_add](roles/shadowman_windows_firewall_add/README.md) | Role for shadowman windows firewall add |
| [shadowman_windows_firewall_remove](roles/shadowman_windows_firewall_remove/README.md) | Role for shadowman windows firewall remove |
| [shadowman_windows_powershell](roles/shadowman_windows_powershell/README.md) | Role for shadowman windows powershell |
| [shadowman_windows_user](roles/shadowman_windows_user/README.md) | Role for shadowman windows user |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| aap_metrics.yml | Playbook for aap metrics | all |
| aap_metrics_api.yml | Playbook for aap metrics api | localhost |
| aap_roi.yml | Playbook for aap roi | localhost |
| ad_user_info.yml | Playbook for ad user info | all |
| addfirewallrule.yml | Playbook for addfirewallrule | {{ vm_name | default('none')}} |
| addvmtoad.yml | Playbook for addvmtoad | {{ vm_name }} |
| buildlinuxreport.yml | Playbook for buildlinuxreport | all |
| buildwindowsreport.yml | Playbook for buildwindowsreport | all |
| certificatereport.yml | Playbook for certificatereport | all |
| change_request_patch.yml | Playbook for change request patch | localhost |
| compliance_enforcement.yml | Playbook for compliance enforcement | all |
| compliancescan.yml | Playbook for compliancescan | all |
| controller_schedule.yml | Playbook for controller schedule | localhost |
| driftcheck.yml | Playbook for driftcheck | all |
| env.yml | Playbook for env | localhost |
| esx_migrate.yml | Playbook for esx migrate | localhost |
| esx_update.yml | Playbook for esx update | all |
| hashisshdconfig.yml | Playbook for hashisshdconfig | all |
| image_builder_image_build.yml | Playbook for image builder image build | all |
| image_builder_install.yml | Playbook for image builder install | all |
| infrapatching.yml | Playbook for infrapatching | all |
| initialconfig.yml | Playbook for initialconfig | {{ vm_name | default('all')}} |
| insights_openscap_setup.yml | Playbook for insights openscap setup | all |
| linux_package.yml | Playbook for linux package | all |
| linuxcis.yml | Playbook for linuxcis | all |
| linuxcompliance.yml | Playbook for linuxcompliance | all |
| linuxkernelcleanup.yml | Playbook for linuxkernelcleanup | all |
| linuxnist.yml | Playbook for linuxnist | all |
| linuxpatching.yml | Playbook for linuxpatching | all |
| linuxpatching_app.yml | Playbook for linuxpatching app | all |
| linuxpatching_lifecycle_test.yml | Playbook for linuxpatching lifecycle test | {{ lifecycle_environment }} |
| linuxpatching_poll.yml | Playbook for linuxpatching poll | all |
| linuxpci.yml | Playbook for linuxpci | all |
| mesh_status.yml | Playbook for mesh status | all |
| nmapsnow.yml | Playbook for nmapsnow | ssh, unreachable_hosts, unreachable_hosts_2 |
| openscap.yml | Playbook for openscap | all |
| openscap windows.yml | Playbook for openscap windows | all |
| patching_withsnapshot.yml | Playbook for patching withsnapshot | all |
| podmancleanup.yml | Playbook for podmancleanup | all |
| podmancleanupedahub.yml | Playbook for podmancleanupedahub | all |
| reboot.yml | Playbook for reboot | all |
| removefirewallrule.yml | Playbook for removefirewallrule | {{ vm_name | default('all')}} |
| removelocaluser.yml | Playbook for removelocaluser | {{ vm_name | default('all')}} |
| removewindowsuser.yml | Playbook for removewindowsuser | {{ vm_name | default('all')}} |
| seal_rhel.yml | Playbook for seal rhel | {{ operating_system | lower }}updates.shadowman.dev |
| seal_rhel_vmware.yml | Playbook for seal rhel vmware | all |
| shadowman_patching.yml | Playbook for shadowman patching | tag_{{ env }}:&tag_{{ owner.split('@')[0] }}* |
| shadowman_patching_snow.yml | Playbook for shadowman patching snow | {{ vm_names }} |
| snapshot_postpatch.yml | Playbook for snapshot postpatch | all |
| snapshot_prepatch.yml | Playbook for snapshot prepatch | all |
| snow_cr_patching.yml | Playbook for snow cr patching | localhost |
| tower_metrics.yml | Playbook for tower metrics | all |
| updateuser_AD.yml | Playbook for updateuser AD | all |
| updateuser_IDM.yml | Playbook for updateuser IDM | localhost |
| vcenter_admin.yml | Playbook for vcenter admin | localhost |
| vmtagsreport.yml | Playbook for vmtagsreport | localhost |
| vmware_prereqs.yml | Playbook for vmware prereqs | all |
| win_package.yml | Playbook for win package | all |
| win_package_choc.yml | Playbook for win package choc | all |
| windows_patching.yml | Playbook for windows patching | all |
| windows_patching_app.yml | Playbook for windows patching app | all |
| windowscis.yml | Playbook for windowscis | all |
| windowsstig.yml | Playbook for windowsstig | all |
| writecsv.yml | Playbook for writecsv | all |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run aap_metrics.yml

# Run in stdout mode
ansible-navigator run aap_metrics.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - shadowman_aap_metrics
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-Config/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
