---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuring SSH to listen only on a private network

You can further secure your server by running SSHd only on the backend network. Therefore, you need to connect to the VPN every time you need to access SSH.

1. Locate the following file. Use this file to define the IP address for `sshd`.
```
# nano /etc/ssh/sshd_config
```

2. Locate the line containing `ListenAddress 0.0.0.0`. If it begins with a '#' character, remove this character. Set the IP address to the IP you would like it to listen on. You can find your internal IP address by selecting *Hardware* from the {{site.data.keyword.slportal_full}}.
3. After you make the change, restart the SSH service:
```
# service sshd restart
```

Your current shell window will not disconnect when you restart the service. Verify that you can connect to the server through the new SSH port before you exit your current shell window. If there is a problem, SSHd fails to restart and you need to connect to the server by using an alternative method.
