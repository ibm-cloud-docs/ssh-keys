---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IPv6 addresses, Linux server, IPv6

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以侦听 IPv6 地址
{: #configuring-ssh-to-listen-on-ipv6-addresses}

使用以下过程在 Linux 服务器上启用 SSH 以侦听 IPv6：
1. 找到文件：/etc/ssh/sshd_config。
2. 找到包含 `ListenAddress` 的行。
3. 取消注释 `#ListenAddress ::` 行：
```
ListenAddress ::
```

此操作会将 `sshd` 绑定到您设备上的每个地址。
