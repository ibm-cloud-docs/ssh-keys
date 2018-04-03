---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以仅侦听专用网络

通过仅在后端网络上运行 SSHd，可以进一步确保服务器的安全。因此，在每次需要访问 SSH 时，都需要连接 VPN。

1. 找到以下文件。使用此文件来定义 `sshd` 的 IP 地址。
```
# nano /etc/ssh/sshd_config
```

2. 找到包含 `ListenAddress 0.0.0.0` 的行。如果该行的开头是“#”字符，请除去此字符。将 IP 地址设置为您要侦听的 IP。您可以通过在 {{site.data.keyword.slportal_full}} 中选择*硬件*来查找内部 IP 地址。
3. 在进行更改之后，请重新启动 SSH 服务：
```
# service sshd restart
```

在重新启动服务时，当前的 shell 窗口不会断开连接。先验证能否通过新的 SSH 端口连接服务器，然后退出当前 shell 窗口。如果有问题，SSHd 重新启动会失败，您需要使用替代方法来连接服务器。
