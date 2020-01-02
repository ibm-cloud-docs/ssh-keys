---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: Red Hat server, main IP address of your server, default options

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connecting to a Red Hat server with SSH
{: #connecting-to-a-redhat-server-with-ssh}

To complete this procedure, you need an SSH client, such as PuTTY, on your home computer. PuTTY is a widely distributed, free SSH client.
In most cases, you can use the default options in PuTTY to successfully connect to your Red Hat server for the first time.

1. Open PuTTY and type in the main IP address of your server into the `'Hostname (or IP address)'` field and click Open.

  The default port for SSH is 22, but you can change it on the server after your first successful connection.
  {:note} 
  
2. The Red Hat server prompts you for a user name and password. Type your root user/pass information for the server.
3. Save the connection details (IP address and port) into Sessions by typing the IP address and port. Create a title for those connection properties such as "My Server" and click Save.
  When you connect to your server, you need to highlight only the saved session and click Open.

You can connect to your server by using the public network.
You can also connect by using the private network. Follow the instructions in the {{site.data.keyword.cloud}} console on connecting to the VPN and then use SSH to connect to your private IP address.
