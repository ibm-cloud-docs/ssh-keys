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

# 编辑 SSH 密钥的详细信息
{: #editing-details-for-an-ssh-key}

在 {{site.data.keyword.cloud}} 控制台中[添加 SSH 密钥](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)之后，就可以编辑密钥详细信息。您可以编辑密钥的**标签**（用于轻松识别 SSH 密钥的短名称）和**注释**。
{:shortdesc}

## 开始之前
首先，导航至设备菜单并确保您有正确的帐户许可权来完成以下任务。

* 导航至控制台的设备菜单。有关更多信息，请参阅[导航至设备](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)。
* 确保您有任何必要的帐户许可权和设备访问权。只有帐户所有者，或具有**管理用户**经典基础架构许可权的用户才可以调整许可权。

有关许可权的更多信息，请参阅[经典基础架构许可权](/docs/iam?topic=iam-infrapermission#infrapermission)和[管理设备访问权](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 编辑 SSH 密钥详细信息

如果需要编辑密钥本身，请除去密钥，然后将正确的密钥添加到 {{site.data.keyword.cloud_notm}} 控制台。与 SSH 密钥详细信息一起列出的指纹并不是密钥本身，而是用于检索密钥的一个简短的字节序列。指纹可能无法以任何方式表示实际的 SSH 密钥。
{:note}

请完成以下步骤来编辑 SSH 密钥详细信息。

1. 从**设备**菜单，选择**管理 > SSH 密钥**。 
2. 在**标签**字段中或者**注释**字段中单击任意位置以打开该字段进行编辑。
3. 在相应字段中输入更新的文本。
4. 单击屏幕中的任意位置以关闭该字段，不再进行编辑。


## 后续步骤

编辑后的 SSH 密钥详细信息将立即在 SSH 密钥列表中更新。
