---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 限制公用網路上的 SSH 存取

SSH 可存取性讓使用者能透過網際網路連線安全地存取裝置。公用及專用網路上的 {{site.data.keyword.cloud}} 裝置上都可使用 SSH。然而，您應該限制公用網路上的 SSH 可存取性，除非有獨特的商業需要。藉由在公用網路上限制 SSH 存取，使用者仍可以在專用網路上存取裝置，但來自於不明使用者在公用網路上存取裝置的風險會得到緩解。如果必須在公用網路上進行 SSH 存取，您可以將 SSH 轉移到自訂埠號，以增加一層安全。
{:shortdesc}

請遵循下列步驟，限制公用網路上的 SSH 存取。
1. 透過 [VPN ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://www.softlayer.com/vpn-access){: new_window} 存取**專用網路**。
2. 透過 SSH 登入裸機伺服器**專用 IP 位址**。
3. 執行下列指令來開啟 `sshd_config` 檔案以進行編輯：
  > `vi /etc/ssh/sshd_config`
4. 從某一 `ListenAddress` 行移除**井字號 (#)**，以解除該行的註解。
5. 在解除註解的 `ListenAddress` 行中，輸入「裸機伺服器」的**專用 IP 位址**。
6. 執行 `:wq` 指令，以儲存變更並結束檔案。
7. 重新啟動 sshd 服務
  > `service sshd restart`
8. 嘗試透過「裸機伺服器」的公用 IP 位址存取 SSH，以測試 SSH 可存取性的更新。<br><br><table border="1"><tr><th>如果連線...</th><th>則...</th></tr><tr><td>無法進行</td><td>對 SSH 可存取性進行的變更成功。不需要任何進一步的動作。</td></tr><tr><td>可以進行</td><td>對 SSH 可存取性進行的變更失敗。請重複先前的步驟，以重試 SSH 限制。如果仍然發生此問題，請與支援中心聯絡。</td></tr></table>

## 後續步驟

成功限制 SSH 存取之後，使用者若未透過專用網路連接，則無法透過 SSH 存取裝置。此動作隨時都可以回復，方法是將井字號 (#) 新增回已解除註解的行，便可將該行還原為註解。
