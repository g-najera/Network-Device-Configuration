Config HA
=========

Used to configure HA peering on devices.


Role Variables
--------------

The following vars are required:

*F5*

* f5_ha_vlan = The VLAN to be used for HA replication
* f5_ha_ports = List of interface ports used for HA Port Channel
* f5_ha_primary_ip = HA Self IP for primary(active) node
* f5_ha_secondary_ip = HA Self IP for secondary(standby) node
* primary = yes or no value to determine which node will be primary
* ha_peer = name of the peer node, the playbook will reference the ansible_host variable of the peer so it must exist in inventory. 

*Nexus*

* nxos_vpc_domain = Domain ID of the VPC domain, if none specified a random one will be generated.
* ha_primary = true or false value to determine which node will be primary
* ha_peer = name of the peer node, the playbook will reference the ansible_host variable of the peer so it must exist in inventory. 

The nxos.yml playbook relies on a data structure set as shown below and can be found in the example found in host_vars/nexus1.yml

```
interface_config:
  - name: Po100
    description: vPC PeerLink
    enabled: True
    portchannel_id: 100
    vpc_peerlink: True
    members:
      - Ethernet1/6
      - Ethernet1/7
```