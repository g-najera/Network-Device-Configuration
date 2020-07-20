Config NTP
=========

Used to configure NTP service on devices.


Role Variables
--------------

The following vars are required:

* ntp_servers = list of ntp servers

```
ntp_servers:
  - 3.3.3.3
  - 3.3.3.4
```