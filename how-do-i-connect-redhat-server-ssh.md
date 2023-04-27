---

copyright:
  years: 2014, 2023
lastupdated: "2023-04-27"

keywords: RedHat server, main IP address of your server, default options

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Connecting to a Red Hat server with SSH
{: #connecting-to-a-redhat-server-with-ssh}

To complete this procedure, you need an SSH client, such as PuTTY. PuTTY is a widely distributed, free SSH client.
In most cases, you can use the default options in PuTTY to successfully connect to your Red Hat server.

1. Open PuTTY and enter the main IP address of your server in the `'Hostname (or IP address)'` field and click **Open**.

    The default port for SSH is 22, but you can change it on the server after your first successful connection.
    {: note}

2. Enter your root user credentials for the server.
3. Save the connection details (IP address and port) into Sessions by entering the IP address and port. Create a title for those connection properties such as "My Server" and click **Save**.
   When you connect to your server, you need to highlight only the saved session and click **Open**.
   {: tip}

You can connect to your server by using the public network. You can also connect by using the private network. Follow the instructions in the {{site.data.keyword.cloud}} console to connect to the VPN and then use SSH to connect to your private IP address.
