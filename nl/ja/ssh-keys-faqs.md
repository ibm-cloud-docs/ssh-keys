---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, SSH key, device-specific

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQ: SSH 鍵
{: #faqs-ssh-keys}

## SSH 鍵はどこにありますか?
{:faq}

SSH 鍵はデバイス固有であり、デバイス内にあります。 オペレーティング・システムはそれぞれ異なるため、SSH 鍵の場所の特定方法は OS 固有です。 デバイス上での SSH 鍵の生成について詳しくは、[SSH 鍵の生成 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window} に関する GitHub の記事を参照してください。

## 何個の SSH 鍵をアカウントに追加できますか?
{:faq}

1 つのアカウントに最大 100 個までの SSH 鍵を関連付けることができます。 許可ユーザーは、{{site.data.keyword.slportal_full}}を使用して 1 回につき [1 個の SSH 鍵](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key)を追加できます。 多くのユーザーには 100 個の鍵は必要ありません。必要ない鍵は削除して、追加の有効鍵のための使用可能スペースを確保してください。 詳しくは、[SSH 鍵の削除](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key)を参照してください。

## 実際の SSH 鍵はリストされていませんが、指紋が表示されています。 これはなんですか?
{:faq}

SSH 鍵の詳細とともに表示されている指紋は、システムによって生成された、省略されたバイト・シーケンスです。 指紋は SSH 鍵自体より短く、関連デバイスの公開鍵の認証やルックアップに使用されます。

## イメージ・テンプレートを使用しているデバイスを作成または再ロードした場合、SSH 鍵は引き継がれますか?
{:faq}

どちらとも言えません。各デバイスは固有の SSH 鍵を持っているため、新しくプロビジョンまたは再ロードされたデバイスの鍵はイメージとは異なります。  ただし、Flex イメージまたは標準イメージ・テンプレートのいずれかに関連付けられた SSH 鍵は、プロビジョンまたは再ロードの際にデバイスに関連付けられます。 また、セットアップ・プロセス中に鍵を追加することもできます。
