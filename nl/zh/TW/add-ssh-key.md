---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 新增 SSH 金鑰
{: #adding-an-ssh-key}

如果您是獲得授權的使用者，則可以新增 SSH 金鑰至您的帳戶。在任一時刻，每個帳戶可以有最多 100 個 SSH 金鑰。SSH 金鑰最常用於 [OS 重新載入程序](/docs/software?topic=software-reloading-the-os#reloading-the-os)，且也可以用於您佈建新裝置時。
{:shortdesc}

## 開始之前
首先，產生公用 SSH 金鑰、導覽至裝置功能表，並確保您具有正確的帳戶許可權來完成作業。

* 針對您的裝置[產生公用 SSH 金鑰 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://help.github.com/articles/generating-ssh-keys){: new_window}。
* 導覽至主控台的裝置功能表。如需相關資訊，請參閱[導覽至裝置](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)。
* 確保您具有任何必要的帳戶許可權及裝置存取權。僅帳戶擁有者或具有**管理使用者**標準基礎架構許可權的使用者才能調整許可權。

如需許可權的相關資訊，請參閱[標準基礎架構許可權](/docs/iam?topic=iam-infrapermission#infrapermission)及[管理裝置存取權](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 將 SSH 金鑰新增至您的帳戶
請完成下列步驟以將 SSH 金鑰新增至您的帳戶。

1. 從**裝置**功能表中，選取**管理 > SSH 金鑰**。
2. 按一下**新增**。
3. 按一下**瀏覽**找到公開金鑰檔，或是手動在**金鑰內容**文字框輸入。
4. 在**標籤**欄位中輸入 SSH 金鑰的**簡稱**。
5. 視需要在**附註**欄位輸入任何適用的附註。
6. 按一下**新增**以新增 SSH 金鑰。 

## 後續步驟

新增 SSH 金鑰之後，它會出現在 SSH 金鑰的清單中。您可以隨時[編輯金鑰詳細資料](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key)。您也可以從清單[移除 SSH 金鑰](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key)。請儘快移除已作廢的 SSH 金鑰，以確定空間可用（如果您需要新增其他金鑰的話）。
