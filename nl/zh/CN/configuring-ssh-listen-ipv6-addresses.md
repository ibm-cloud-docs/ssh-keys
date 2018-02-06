---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以侦听 IPv6 地址

使用以下过程在 Linux 服务器 SSH 上启用 IPv6：
1. 找到文件：/etc/ssh/sshd_config。
2. 找到包含 `ListenAddress` 的行。
3. 取消注释 `#ListenAddress ::` 行：
```
ListenAddress ::
```

此操作会将 `sshd` 绑定到您设备上的每个地址。
