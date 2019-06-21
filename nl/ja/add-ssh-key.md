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

# SSH 鍵の追加
{: #adding-an-ssh-key}

許可ユーザーの場合、アカウントに SSH 鍵を追加することができます。 各アカウントは、いつでも最大 100 個までの SSH 鍵を持つことができます。 SSH 鍵は [OS 再ロード・プロセス](/docs/software?topic=software-reloading-the-os#reloading-the-os)で最もよく使用され、また新規デバイスをプロビジョンするときにも使用できます。{:shortdesc}

## 始めに
まず、公開 SSH 鍵を生成し、デバイス・メニューに移動して、タスクを完了するための適切なアカウント権限があることを確認します。

* デバイス用に [SSH 鍵を生成します ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://help.github.com/articles/generating-ssh-keys){: new_window}。
* コンソールのデバイス・メニューに移動します。詳しくは、[デバイスへのナビゲート](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)を参照してください。
* 必要なアカウント権限とデバイス・アクセス権限があることを確認します。アカウントの所有者、またはクラシック・インフラストラクチャーの**「ユーザーの管理」**権限を持つユーザーのみが権限を調整できます。

権限について詳しくは、[クラシック・インフラストラクチャーの権限](/docs/iam?topic=iam-infrapermission#infrapermission)および[デバイス・アクセス権限の管理](/docs/vsi?topic=virtual-servers-managing-device-access)を参照してください。

## アカウントへの SSH 鍵の追加
以下のステップに従って、SSH 鍵をアカウントに追加します。

1. **「デバイス」**メニューから、**「管理」>「SSH 鍵」**を選択します。
2. **「追加」**をクリックします。
3. **「参照」**をクリックして公開鍵ファイルを見つけるか、**「鍵のコンテンツ」**テキスト・ボックスに手動で入力します。
4. **「ラベル」**フィールドに SSH 鍵の**ショート・ネーム**を入力します。
5. 必要に応じて、**「メモ」**フィールドに該当するメモを入力します。
6. **「追加」**をクリックして SSH 鍵を追加します。  

## 次のステップ

SSH 鍵を追加すると、その鍵は SSH 鍵リストに表示されます。
[鍵の詳細はいつでも編集](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key)できます。 また、リストから [SSH 鍵を削除](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key)することもできます。 廃止された SSH 鍵はできるだけ速やかに削除し、さらに鍵を追加する必要が生じた場合に備えてスペースを利用可能にしておくようにしてください。
