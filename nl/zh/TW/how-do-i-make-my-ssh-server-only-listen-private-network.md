---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以便只接聽專用網路
{: #configuring-ssh-to-listen-only-on-a-private-network}

您可以只在後端網路執行 SSH，進一步保護您的伺服器。因此，每次您需要存取 SSH 時便需要連接至 VPN。

1. 找到下列檔案。請使用這個檔案來定義 `sshd` 的 IP 位址。
```
# nano /etc/ssh/sshd_config
```

2. 找到包含 `ListenAddress 0.0.0.0` 的行。如果它開頭為 '#' 字元，請移除此字元。將 IP 位址設為您要接聽的 IP。您可以從 {{site.data.keyword.slportal_full}} 選取*硬體* 來找到您的內部 IP 位址。
3. 變更之後，重新啟動 SSH 服務：
```
# service sshd restart
```

當您重新啟動服務時，您的現行 Shell 視窗不會中斷連線。請驗證您可以透過新的 SSH 埠連接至伺服器，然後才結束現行 Shell 視窗。如果有問題，SSHd 將無法重新啟動，且您將需要使用替代方法連接至伺服器。
