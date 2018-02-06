---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 添加 SSH 密钥

如果您是授权用户，那么可以将 SSH 密钥添加到您的帐户。每个帐户都可以随时拥有多达 100 个 SSH 密钥。在 {{site.data.keyword.slportal_full}} 中，SSH 密钥最常用在[操作系统重装流程](../software/vsi_reload_os.html){:new_window}中，也可以用在供应新设备时。 

**注：**先为您要添加密钥的设备[生成公共 SSH 密钥 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://help.github.com/articles/generating-ssh-keys){: new_window}，然后再为帐户添加 SSH 密钥。 

按照下列步骤为帐户添加 SSH 密钥。
1. 访问 **SSH 密钥**屏幕。请参阅 [SSH 密钥入门](index.html)。
2. 单击屏幕顶部的**添加**选项卡。
3. 单击**浏览**找到公用密钥文件或者在**密钥内容**文本框中手动输入密钥文件。
4. 在**标签**字段中输入 SSH 密钥的**短名称**。
5. 根据需要在**注释**字段中输入适当的注释。
6. 单击**添加**以添加 SSH 密钥。单击**取消**以取消该操作。

## 后续步骤

添加 SSH 密钥之后，它将显示在 SSH 密钥列表中。您随时可以[编辑密钥详细信息](edit-details-ssh-key.html)。也可以从列表中[除去 SSH 密钥](remove-ssh-key.html){:new_window}。尽快除去过时的 SSH 密钥，这样可以确保在需要添加更多密钥时有可用的空间。
