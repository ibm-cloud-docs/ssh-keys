---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 除去 SSH 密钥
{: #removing-an-ssh-key}

当存储在 {{site.data.keyword.cloud}} 控制台中的 SSH 密钥过时或不再需要时，可以除去该密钥。尽快除去过时的 SSH 密钥，以确保有足够的空间容纳更多有效密钥。
{:shortdesc}

## 开始之前
首先，导航至设备菜单并确保您有正确的帐户许可权来完成以下任务。

* 导航至控制台的设备菜单。有关更多信息，请参阅[导航至设备](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)。
* 确保您有任何必要的帐户许可权和设备访问权。只有帐户所有者，或具有**管理用户**经典基础架构许可权的用户才可以调整许可权。

有关许可权的更多信息，请参阅[经典基础架构许可权](/docs/iam?topic=iam-infrapermission#infrapermission)和[管理设备访问权](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 除去 SSH 密钥

1. 从**设备**菜单，选择**管理 > SSH 密钥**。
2. 对于您要除去的 SSH 密钥，单击它旁边的**除去**图标。
3. 单击**是**以确认。 

## 后续步骤

在除去 SSH 密钥之后，会从列表中立即将其除去。在您供应新设备或在现有设备上执行系统重装时，无法再使用该密钥。如果错误地除去了密钥，或者需要将密钥添加回 {{site.data.keyword.cloud_notm}} 控制台，请参阅[添加 SSH 密钥](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)。
