---

copyright:
  years: 2014, 2023
lastupdated: "2023-04-27"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Configuring SSH to listen only on a private network
{: #configuring-ssh-to-listen-only-on-a-private-network}

You can further secure your server by running SSHd only on the backend network. Therefore, you need to connect to the VPN every time you need to access SSH.

1. Locate the following file. Use this file to define the IP address for `sshd`.

   ```
   # nano /etc/ssh/sshd_config
   ```
   {: pre}

2. Locate the line that contains `ListenAddress 0.0.0.0`. If it begins with a '#' character, remove this character. Set the IP address to the IP that you want to listen on. You can find your internal IP address by selecting ***Hardware** from the {{site.data.keyword.cloud}} console.

3. After you make the change, restart the SSH service:

   ```
   # service sshd restart
   ```
   {: pre}

Your shell window doesn't disconnect when you restart the service. Verify that you can connect to the server through the new SSH port before you exit your current shell window. If a problem occurs, SSH fails to restart and you need to connect to the server by using an alternative method.
