---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connecting to a RedHat server with SSH

To complete this procedure, you need an SSH client, such as PuTTY, on your home computer. PuTTY is a widely distributed, free SSH client.
In most cases, you can use the default options in PuTTY to successfully connect to your RedHat server for the first time.

1. Open PuTTY and type in the main IP address of your server into the `'Hostname (or IP address)'` field and click Open.
  Note: The default port for SSH is 22, but you can change it on the server after your first successful connection.
2. The RedHat server prompts you for a user name and password. Type your root user/pass information for the server.
3. Save the connection details (IP address and port) into Sessions by typing the IP address and port. Create a title for those connection properties such as "My Server" and click Save.
  When you connect to your server, you need to only highlight the saved session and click Open.

You can connect to your server by using the public network.
You can also connect by using the private network. Follow the instructions in the {{site.data.keyword.slportal_full}} on connecting to the VPN and then use SSH to connect to your private IP address.