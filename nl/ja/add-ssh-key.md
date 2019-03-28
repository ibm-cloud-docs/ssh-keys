---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH 鍵の追加
{: #adding-an-ssh-key}

許可ユーザーの場合、アカウントに SSH 鍵を追加することができます。 各アカウントは、いつでも最大 100 個までの SSH 鍵を持つことができます。 {{site.data.keyword.slportal_full}}内で、SSH 鍵は [OS 再ロード・プロセス](/docs/infrastructure/software?topic=software-reloading-the-os)で最もよく使用され、また新規デバイスをプロビジョンするときにも使用できます。

**注:** SSH 鍵をアカウントに追加する前に、鍵を追加するデバイスで[公開 SSH 鍵を生成 ![外部リンク・アイコン ](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://help.github.com/articles/generating-ssh-keys){: new_window} してください。

以下のステップに従って、SSH 鍵をアカウントに追加します。
1. **「SSH 鍵」**画面にアクセスします。 [SSH 鍵入門](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial)を参照してください。
2. **「追加」**をクリックします。
3. **「参照」**をクリックして公開鍵ファイルを見つけるか、**「鍵のコンテンツ」**テキスト・ボックスに手動で入力します。
4. **「ラベル」**フィールドに SSH 鍵の**ショート・ネーム**を入力します。
5. 必要に応じて、**「メモ」**フィールドに該当するメモを入力します。
6. **「追加」**をクリックして SSH 鍵を追加します。 操作をキャンセルするには、**「キャンセル」**をクリックします。

## 次のステップ

SSH 鍵を追加すると、その鍵は SSH 鍵リストに表示されます。
[鍵の詳細はいつでも編集](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key)できます。 また、リストから [SSH 鍵を削除](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key)することもできます。 廃止された SSH 鍵はできるだけ速やかに削除し、さらに鍵を追加する必要が生じた場合に備えてスペースを利用可能にしておくようにしてください。
