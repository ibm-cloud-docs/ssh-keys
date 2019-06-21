---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH keys, SSH key, device-specific

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# 常见问题：SSH 密钥
{: #faqs-ssh-keys}

## 在哪能找到我的 SSH 密钥？
{:faq}

SSH 密钥是特定于设备的，可以在设备中找到。因为每个操作系统不同，所以找到 SSH 密钥的步骤因操作系统而异。要了解有关在设备上生成 SSH 密钥的更多信息，请参阅[生成 SSH 密钥 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window} 中的 GitHub 的文章。

## 我可以在帐户中添加多少个 SSH 密钥？
{:faq}

您可以为一个帐户关联最多 100 个 SSH 密钥。授权用户可以使用 {{site.data.keyword.cloud}} 控制台一次[添加 1 个 SSH 密钥](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key)。虽然大多数用户不需要 100 个密钥，但还是应该除去不再需要的密钥，以确保有空间可以容纳更多有效密钥。有关更多信息，请参阅[除去 SSH 密钥](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key)。

## 我的实际 SSH 密钥没列出来，但我看到了指纹。那是什么？
{:faq}

在显示 SSH 密钥详细信息的同时也会显示指纹，指纹是系统生成的字节序列缩写。指纹比 SSH 密钥本身短，用于认证或查找关联的设备的公用密钥。

## 如果我创建或重新装入使用映像模板的设备，SSH 密钥会持续可用吗？
{:faq}

是，也不是。每个设备都有唯一的 SSH 密钥，所以新供应的或重新装入的设备的密钥与映像的密钥不同。但是与 flex 镜像或标准映像模板相关联的 SSH 密钥在供应设备或重新装入设备时是与设备关联的。您还可以在设置过程中添加密钥。
