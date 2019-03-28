---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: RedHat server, main IP address of your server, default options

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 使用 SSH 連接至 RedHat 伺服器
{: #connecting-to-a-redhat-server-with-ssh}

若要完成此程序，您的起始電腦上需要有 SSH 用戶端，例如 PuTTY。PuTTY 是廣泛散佈的免費 SSH 用戶端。在大部分情況下，您在 PuTTY 中使用預設選項，即可第一次便順利連接至 RedHat 伺服器。

1. 開啟 PuTTY 並將伺服器的主要 IP 位址鍵入到 `'Hostname (or IP address)'` 欄位，並按一下 Open。附註：SSH 的預設埠是 22，但第一次成功連線之後可以在伺服器上變更它。
2. RedHat 伺服器會提示您輸入使用者名稱及密碼。請鍵入伺服器的 root 使用者/密碼資訊。
3. 鍵入 IP 位址及埠，將連線詳細資料（IP 位址及埠）儲存到階段作業。為那些連線內容建立一個標題，例如 "My Server"，然後按一下「儲存」。當您連接至伺服器時，只需要強調顯示已儲存的階段作業，然後按一下「開啟」。

您可以使用公用網路連接至伺服器。也可以使用專用網路連接。請遵循 {{site.data.keyword.slportal_full}} 中關於連接至 VPN 的指示，然後使用 SSH 連接至您的專用 IP 位址。
