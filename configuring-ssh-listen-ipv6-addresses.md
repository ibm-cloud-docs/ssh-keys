---

copyright:
  years: 2014, 2023
lastupdated: "2018-02-23"

keywords: IPv6 addresses, Linux server, IPv6

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Configuring SSH to listen on IPv6 addresses
{: #configuring-ssh-to-listen-on-ipv6-addresses}

Use the following procedure to enable SSH on a Linux server to listen on IPv6.

1. Locate the file: /etc/ssh/sshd_config.
2. Locate the line that contains `ListenAddress`.
3. Uncomment the `#ListenAddress ::` the following line to bind `sshd` to every address on your device.

    ```ListenAddress ::```
