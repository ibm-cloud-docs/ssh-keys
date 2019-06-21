---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH key, key details, IBM Cloud infrastructure customer

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 編輯 SSH 金鑰的詳細資料
{: #editing-details-for-an-ssh-key}

在 {{site.data.keyword.cloud}} 主控台[新增 SSH 金鑰](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)之後，您可以編輯金鑰詳細資料。您可以編輯金鑰的**標籤**（用來輕鬆識別 SSH 金鑰的簡稱）和**附註**。
{:shortdesc}

## 開始之前
首先，導覽至裝置功能表，並確保您具有正確的帳戶許可權來完成作業。

* 導覽至主控台的裝置功能表。如需相關資訊，請參閱[導覽至裝置](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)。
* 確保您具有任何必要的帳戶許可權及裝置存取權。僅帳戶擁有者或具有**管理使用者**標準基礎架構許可權的使用者才能調整許可權。

如需許可權的相關資訊，請參閱[標準基礎架構許可權](/docs/iam?topic=iam-infrapermission#infrapermission)及[管理裝置存取權](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 編輯 SSH 金鑰詳細資料

如果您需要編輯金鑰本身，請移除金鑰，然後將正確金鑰新增至 {{site.data.keyword.cloud_notm}} 主控台。與 SSH 金鑰詳細資料一起列出的指紋不是金鑰本身；它是在擷取金鑰時用到的位元組短序列。指紋可能不以任何形式代表實際的 SSH 金鑰。
{:note}

請完成下列步驟以編輯 SSH 金鑰詳細資料。

1. 從**裝置**功能表中，選取**管理 > SSH 金鑰**。 
2. 按一下**標籤**欄位或**附註**欄位的任意處，以開啟欄位進行編輯。
3. 在對應的欄位中鍵入更新過的文字。
4. 按一下畫面上的任意處，以關閉欄位，進行其他編輯。


## 後續步驟

編輯過的 SSH 金鑰詳細資料會立即在 SSH 金鑰清單中更新。
