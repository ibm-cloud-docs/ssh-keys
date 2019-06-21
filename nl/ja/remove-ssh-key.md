---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH 鍵の削除
{: #removing-an-ssh-key}

{{site.data.keyword.cloud}} コンソールに保管されている SSH 鍵が廃止された場合やもう必要なくなった場合は、鍵を削除できます。廃止された SSH 鍵はできるだけ速やかに削除して、追加の有効鍵のための十分なスペースを確保するようにしてください。{:shortdesc}

## 始めに
まず、デバイス・メニューに移動して、タスクを完了するための適切なアカウント権限があることを確認します。

* コンソールのデバイス・メニューに移動します。詳しくは、[デバイスへのナビゲート](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)を参照してください。
* 必要なアカウント権限とデバイス・アクセス権限があることを確認します。アカウントの所有者、またはクラシック・インフラストラクチャーの**「ユーザーの管理」**権限を持つユーザーのみが権限を調整できます。

権限について詳しくは、[クラシック・インフラストラクチャーの権限](/docs/iam?topic=iam-infrapermission#infrapermission)および[デバイス・アクセス権限の管理](/docs/vsi?topic=virtual-servers-managing-device-access)を参照してください。

## SSH 鍵の削除

1. **「デバイス」**メニューから、**「管理」>「SSH 鍵」**を選択します。
2. 削除する SSH 鍵の横の**「削除」**アイコンをクリックします。
3. **「はい」**をクリックして確認します。  

## 次のステップ

SSH 鍵を削除すると、その鍵はリストから即時削除されます。 この鍵は、新規デバイスをプロビジョンしたり既存のデバイスで OS 再ロードを実行したりする際にはもう使用できません。 鍵を誤って削除した場合、または {{site.data.keyword.cloud_notm}} コンソールに追加し直す必要がある場合は、[SSH 鍵の追加](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)を参照してください。
