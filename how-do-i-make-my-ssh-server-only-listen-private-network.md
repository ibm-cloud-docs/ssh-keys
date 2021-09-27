---

copyright:
  years: 2014, 2021
lastupdated: "2021-09-27"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}

# Configuring SSH to listen only on a private network
{: #configuring-ssh-to-listen-only-on-a-private-network}

You can further secure your server by running SSHd only on the backend network. Therefore, you need to connect to the VPN every time you need to access SSH.

1. Locate the following file. Use this file to define the IP address for `sshd`.

   ```
   # nano /etc/ssh/sshd_config
   ```
   {: pre}

2. Locate the line containing `ListenAddress 0.0.0.0`. If it begins with a '#' character, remove this character. Set the IP address to the IP you would like it to listen on. You can find your internal IP address by selecting *Hardware* from the {{site.data.keyword.cloud}} console.

3. After you make the change, restart the SSH service:

   ```
   # service sshd restart
   ```
   {: pre}

Your current shell window will not disconnect when you restart the service. Verify that you can connect to the server through the new SSH port before you exit your current shell window. If there is a problem, SSHd fails to restart and you need to connect to the server by using an alternative method.
