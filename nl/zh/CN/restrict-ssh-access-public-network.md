---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 限制公用网络上的 SSH 访问

SSH 可访问性让用户能够通过因特网连接对设备进行安全访问。在公用网络和专用网络上，SSH 在 {{site.data.keyword.cloud}} 设备上都可用。但除非有特殊的业务需求，否则应限制公用网络上的 SSH 可访问性。通过限制公用网络上的 SSH 访问，用户仍可通过专用网络访问设备，但公用网络上未知用户访问设备的风险得到了缓解。如果需要通过公用网络进行 SSH 访问，那么可以将 SSH 转移到定制端口号以增加一层安全保护。
{:shortdesc}

按照下列步骤来限制通过公用网络进行 SSH 访问。
1. 通过 [VPN ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://www.softlayer.com/vpn-access){: new_window} 访问**专用网络**。
2. 通过 SSH 登录裸机服务器**专用 IP 地址**。
3. 运行以下命令以打开 `sshd_config` 文件进行编辑：
  > `vi /etc/ssh/sshd_config`
4. 从一个 `ListenAddress` 行中除去井号 **#** 以取消对该行的注释。
5. 在取消注释的 `ListenAddress` 行中输入裸机服务器的**专用 IP 地址**。
6. 运行 `:wq` 命令以保存更改并退出该文件。
7. 重新启动 sshd 服务
  > `service sshd restart`
8. 尝试通过裸机服务器的公用 IP 地址访问 SSH，以测试对 SSH 可访问性的更新。<br><br><table border="1"><tr><th>如果连接...</th><th>那么...</th></tr><tr><td>无法建立连接</td><td>成功更改了 SSH 可访问性。不需要执行进一步操作。</td></tr><tr><td>可以建立连接</td><td>更改 SSH 可访问性失败。重复先前步骤以重试 SSH 限制。如果问题仍然存在，请联系支持人员。</td></tr></table>

## 后续步骤

成功限制 SSH 访问后，用户在未通过专用网络进行连接时，将无法通过 SSH 访问设备。可随时通过将井号 (#) 添加回取消注释的行来使该行恢复为注释，从而撤销此操作。
