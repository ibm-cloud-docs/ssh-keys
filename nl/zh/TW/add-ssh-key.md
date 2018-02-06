---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 新增 SSH 金鑰

如果您是獲得授權的使用者，則可以新增 SSH 金鑰至您的帳戶。在任一時刻，每個帳戶可以有最多 100 個 SSH 金鑰。在 {{site.data.keyword.slportal_full}} 內，SSH 金鑰最常用於 [OS 重新載入程序](../software/vsi_reload_os.html){:new_window}，且也可以用於您佈建新裝置時。 

**附註：**請先使用您正在為其新增金鑰的裝置[產生公用 SSH 金鑰 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://help.github.com/articles/generating-ssh-keys){: new_window}，然後才將 SSH 金鑰新增至您的帳戶。 

請遵循下列步驟以將 SSH 金鑰新增至您的帳戶。
1. 存取 **SSH 金鑰**畫面。請參閱[開始使用 SSH 金鑰](index.html)。
2. 按一下畫面頂端的**新增**標籤。
3. 按一下**瀏覽**找到公開金鑰檔，或是手動在**金鑰內容**文字框輸入。
4. 在**標籤**欄位中輸入 SSH 金鑰的**簡稱**。
5. 視需要在**附註**欄位輸入任何適用的附註。
6. 按一下**新增**以新增 SSH 金鑰。按一下**取消**即可取消動作。

## 後續步驟

新增 SSH 金鑰之後，它會出現在 SSH 金鑰的清單中。您可以隨時[編輯金鑰詳細資料](edit-details-ssh-key.html)。您也可以從清單[移除 SSH 金鑰](remove-ssh-key.html){:new_window}。請儘快移除已作廢的 SSH 金鑰，以確定空間可用（如果您需要新增其他金鑰的話）。
