---

copyright:
  years: 2014, 2023
lastupdated: "2023-04-27"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Configuring SSH to run on a nonstandard port
{: #configuring-ssh-to-run-on-a-non-standard-port}

Use the following steps to force SSH to run on a nonstandard port:

1. Open `/etc/ssh/sshd_config` in a text editor. The following example is for vi editor.

   ```text
   # vi /etc/ssh/sshd_config
   ```
   {: pre}

2. BrowGose to the following line:

   _# Port 22_

3. Uncomment and edit this line to reflect the new port. You can set this port to any nonstandard port.

   ```text
   Port 2255
   ```
   {: pre}

4. Save and quit the file, and restart SSH.

   ```text
   # /etc/init.d/sshd restart
   ```
   {: pre}

5. If you are connected to the server by using SSH on port 22, you need to reconnect by using the new port.
