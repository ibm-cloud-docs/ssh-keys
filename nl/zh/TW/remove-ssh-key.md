---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 移除 SSH 金鑰
{: #removing-an-ssh-key}

當儲存在 {{site.data.keyword.cloud}} 主控台上的 SSH 金鑰已作廢或不再需要時，您可以移除該金鑰。請儘快移除已作廢的 SSH 金鑰，以確定有足夠的空間給其他有效金鑰使用。
{:shortdesc}

## 開始之前
首先，導覽至裝置功能表，並確保您具有正確的帳戶許可權來完成作業。

* 導覽至主控台的裝置功能表。如需相關資訊，請參閱[導覽至裝置](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)。
* 確保您具有任何必要的帳戶許可權及裝置存取權。僅帳戶擁有者或具有**管理使用者**標準基礎架構許可權的使用者才能調整許可權。

如需許可權的相關資訊，請參閱[標準基礎架構許可權](/docs/iam?topic=iam-infrapermission#infrapermission)及[管理裝置存取權](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 移除 SSH 金鑰

1. 從**裝置**功能表中，選取**管理 > SSH 金鑰**。
2. 按一下您要移除之 SSH 金鑰旁的**移除**圖示。
3. 按一下**是**以進行確認。 

## 後續步驟

移除 SSH 金鑰之後，它會立即從清單移除。當您佈建新的裝置時，或是在現有裝置上執行 OS 重新載入時，無法再使用該金鑰。若是誤將金鑰移除，或是金鑰需要新增回到 {{site.data.keyword.cloud_notm}} 主控台，請參閱[新增 SSH 金鑰](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)。
