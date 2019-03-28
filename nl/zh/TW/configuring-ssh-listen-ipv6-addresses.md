---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IPv6 addresses, Linux server, IPv6

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以接聽 IPv6 位址
{: #configuring-ssh-to-listen-on-ipv6-addresses}

請使用下列程序在 Linux 伺服器上啟用 SSH，以接聽 IPv6：
1. 找到檔案 /etc/ssh/sshd_config。
2. 找到包含 `ListenAddress` 的行。
3. 解除註解 `#ListenAddress ::` 行：
```
ListenAddress ::
```

這樣會將 `sshd` 連結至您裝置上的每個位址。
