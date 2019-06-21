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

# 添加 SSH 密钥
{: #adding-an-ssh-key}

如果您是授权用户，那么可以将 SSH 密钥添加到您的帐户。每个帐户都可以随时拥有多达 100 个 SSH 密钥。SSH 密钥最常用在[操作系统重装流程](/docs/software?topic=software-reloading-the-os#reloading-the-os)中，也可以在供应新设备时使用。
{:shortdesc}

## 开始之前
首先，生成公用 SSH 密钥，导航至设备菜单，并确保您有正确的帐户许可权来完成以下任务。

* 为您的设备[生成公用 SSH 密钥 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://help.github.com/articles/generating-ssh-keys){: new_window}。
* 导航至控制台的设备菜单。有关更多信息，请参阅[导航至设备](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)。
* 确保您有任何必要的帐户许可权和设备访问权。只有帐户所有者，或具有**管理用户**经典基础架构许可权的用户才可以调整许可权。

有关许可权的更多信息，请参阅[经典基础架构许可权](/docs/iam?topic=iam-infrapermission#infrapermission)和[管理设备访问权](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 将 SSH 密钥添加到帐户
请完成以下步骤以向您的帐户添加 SSH 密钥。

1. 从**设备**菜单，选择**管理 > SSH 密钥**。
2. 单击**添加**。
3. 单击**浏览**找到公用密钥文件或者在**密钥内容**文本框中手动输入密钥文件。
4. 在**标签**字段中输入 SSH 密钥的**短名称**。
5. 根据需要在**注释**字段中输入适当的注释。
6. 单击**添加**以添加 SSH 密钥。 

## 后续步骤

添加 SSH 密钥之后，它将显示在 SSH 密钥列表中。您随时可以[编辑密钥详细信息](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key)。也可以从列表中[除去 SSH 密钥](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key)。尽快除去过时的 SSH 密钥，这样可以确保在需要添加更多密钥时有可用的空间。
