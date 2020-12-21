# Ansible-Main
Demos for Ansible Use for configuration of RHEL 7/8 and Windows

# Roles
Current role in requirements.yml is for patching Linux and installing EAP

# Templates
add_motd
>adds a custom MOTD to the server

# Playbooks
compliancescan.yml
>Runs Insights Compliance Scan per plan created in cloud.redhat.com

config_rhel.yml
>tasks for configuration of RHEL 7 and 8 to include activation key and repos

config_windows.yml
>tasks to setup windows timezone

eapappinstall.yml
>installs eap application mazewars

eapinstall.yml
>installs eap on server and sets up firewall

initialconfig.yml
>calls appropriate config tasks based on OS

insights_openscap_setup.yml
>installs and sets up insights and openscap on RHEL servers

linuxpatching.yml
>Using Linux patching role to patch all hosts

osprint.yml
>Prints the inventory hostname and operating system

packageupdate.yml
>Allows you to install or uninstall any package. Variable {{ package }} and {{ state }} must be filled in

win_software_update.yml
>Allows you to install or uninstall any package on Windows using Chocolatey

windows_patching.yml
>Allows you to patch Windows servers using WSUS
