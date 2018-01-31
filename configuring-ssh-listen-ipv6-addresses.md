---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuring SSH to listen on IPv6 addresses

Use the following procedure to enable SSH on a Linux server to listen on IPv6:
1. Locate the file: /etc/ssh/sshd_config.
2. Locate the line that contains `ListenAddress`.
3. Uncomment the `#ListenAddress ::` line:
```
ListenAddress ::
```

This binds `sshd` to every address on your device.
