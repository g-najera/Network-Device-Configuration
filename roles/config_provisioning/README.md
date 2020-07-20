Config Provisioning
=========

Used to provision devices (hostnames, features, misc cofigurations)


Role Variables
--------------

The following vars are required:


*Nexus*

* nxos_features = list of features to enable for Nexus devices

```
nxos_features:
  - "privilege"
  - "vpc"
  - "lacp"
  - "lldp"
  - "tacacs+"
```