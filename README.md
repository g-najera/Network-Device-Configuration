# Network Device Configuration

Ansible network roles created to give customers/consumers a starting point to automating across Arista, Cisco Nexus, Cisco IOS and F5 devices.

## Usage

The following roles perform the following functions:

* **config_aaa**: Configure authentication/authorization tasks on devices.
* **config_acl**: Mostly used to create/update management ACLs but can be modified to push ACLs for network traffic as well.
* **config_audit**: Work in progress, will compare current running config to backups taken in config_backups role.
* **config_backup**: Backup network devices and store them in a separate GIT repo
* **config_credentials**: Update user credentials for local accounts (admin, root, etc)
* **config_dns**: Configures DNS servers
* **config_ntp**: Configures NTP servers
* **config_provisioning**: Configures misc changes such as hostnames, Nexus features or anything that doesn't pertain to the other roles
* **config_snmp**: Configures SNMP servers (mostly focused on SNMPv3)
* **config_syslog**: Configures remote/local syslog settings.

* **Facts**: Gather facts from various device vendors

* **f5_config**: Example Infrastructure as Code role for deploying objects on F5s.



## Required Vars


## Example playbook

```
- name: Configure NTP Servers
  hosts: all
  gather_facts: no

  roles:
    - config_ntp
 ```
## Recommendations

I strongly recommend testing in a lab first to ensure the changes comply with your desired state.
