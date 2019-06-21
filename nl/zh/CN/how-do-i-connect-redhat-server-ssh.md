---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: RedHat server, main IP address of your server, default options

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 利用 SSH 连接 RedHat 服务器
{: #connecting-to-a-redhat-server-with-ssh}

要完成此过程，需要家用计算机上有 SSH 客户机（如 PuTTY）。PuTTY 是一种分布广泛的免费 SSH 客户机。在大多数情况下，第一次都可以使用 PuTTY 中的缺省选项成功连接到 RedHat 服务器。

1. 打开 PuTTY，并将服务器的主 IP 地址输入`“主机名（或 IP 地址）”`字段，然后单击“打开”。

  SSH 的缺省端口是 22，但在第一次成功连接后，可以在服务器上进行更改。
  {:note} 
  
2. RedHat 服务器会提示您输入用户名和密码。输入服务器的 root 用户/密码信息。
3. 通过输入 IP 地址和端口，将连接详细信息（IP 地址和端口）保存到会话中。为这些连接属性创建标题（如“我的服务器”），然后单击“保存”。连接服务器时，需要仅突出显示已保存的会话，然后单击“打开”。

既可以使用公用网络来连接服务器，也可以使用专用网络来连接。遵照 {{site.data.keyword.cloud}} 控制台中关于连接 VPN 的指示信息执行，然后使用 SSH 连接专用 IP 地址。
