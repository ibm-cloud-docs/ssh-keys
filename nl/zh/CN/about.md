---

copyright:
  years: 2014, 2018
lastupdated: "2018-08-15"

keywords: SSH keys, public-key cryptography, SSH

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 关于 SSH 密钥
{: #about-ssh-keys}

SSH 服务器使用 SSH 密钥通过公用密钥密码术来识别用户或设备。SSH 密钥由字母数字组成，分配给设备的 SSH 密钥都是唯一的。授权的用户可以随时使用 {{site.data.keyword.slportal_full}} 添加、编辑或删除 SSH 密钥。

可以在供应期间或通过[操作系统重装](/docs/infrastructure/software?topic=software-reloading-the-os)来请求 SSH 密钥。


利用 SSH 密钥，无需使用密码即可从在设备上实现的每个公用密钥所对应的客户机来访问设备。通过向设备中添加 SSH 密钥，得到 SSH 密钥的设备无需使用密码即可访问相应密钥的设备。
