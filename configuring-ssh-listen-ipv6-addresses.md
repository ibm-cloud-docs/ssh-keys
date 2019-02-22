---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

subcollection: ssh-keys
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
