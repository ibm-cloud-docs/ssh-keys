---

copyright:
  years: 2014, 2021
lastupdated: "2021-09-09"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuring SSH to run on a non-standard port
{: #configuring-ssh-to-run-on-a-non-standard-port}

Complete the following steps to force SSH to run on a non-standard port:

1. Open /etc/ssh/sshd_config in a text editor. The following example is for vi editor.

   ```text
   # vi /etc/ssh/sshd_config
   ```
   {: pre}
 
2. Browse to the following line:
 
   _# Port 22_
 
3. Uncomment and edit this line to reflect the new port. (You can set this port to any non-standard port)

   ```text
   Port 2255 
   ``` 
   {: pre}
 
4. Save and quit the file, and restart SSH.

   ```text
   # /etc/init.d/sshd restart
   ```
   {: pre}

5. If you are connected to the server using SSH on port 22, your connection will drop and you will need to reconnect using the new port.
