---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuring SSH to run on a non-standard port
{: #configuring-ssh-to-run-on-a-non-standard-port}

Follow these steps to force SSH to run on a non-standard port:

1. Open /etc/ssh/sshd_config in a text editor. The following example is for vi editor.
```
# vi /etc/ssh/sshd_config
```

2. Browse to the following line:
```
# Port 22
```

3. Uncomment and edit this line to reflect the new port.
```
Port 2255
```
(this can be set to any non-standard port)

4. Save and quit the file, and restart SSH.
```
# /etc/init.d/sshd restart
```

5. If you are connected to the server using SSH on port 22, your connection will drop and you will need to reconnect using the new port.
