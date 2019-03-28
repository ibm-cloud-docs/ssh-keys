---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IPv6 addresses, Linux server, IPv6

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IPv6 アドレスで listen するための SSH の構成
{: #configuring-ssh-to-listen-on-ipv6-addresses}

Linux サーバーの SSH を使用可能にして IPv6 を listen するには、以下の手順を使用します。
1. ファイル /etc/ssh/sshd_config を見つけます。
2. `ListenAddress` が含まれている行を見つけます。
3. 以下のようにして、`#ListenAddress ::` 行をアンコメントします。
```
ListenAddress ::
```

これにより、`sshd` がデバイス上のすべてのアドレスにバインドされます。
