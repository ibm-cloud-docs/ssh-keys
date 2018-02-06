---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 關於 SSH 金鑰 

SSH 金鑰由 SSH 伺服器用來透過公開金鑰加密法識別使用者或裝置。SSH 金鑰包含英數組合，且對於它們指派到的裝置而言是唯一的。獲得授權的使用者可以隨時使用 {{site.data.keyword.slportal_full}} 新增、編輯或刪除 SSH 金鑰。

SSH 金鑰允許存取裝置，而不必針對裝置上實作的每個公開金鑰使用來自對應用戶端的密碼。藉由將 SSH 金鑰新增至裝置（這可以在佈建期間進行，或透過 [OS 重新載入](../software/vsi_reload_os.html)進行），提供有 SSH 金鑰的裝置會存取對應金鑰的裝置，而不使用密碼。
