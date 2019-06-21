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

# SSH 鍵の詳細の編集
{: #editing-details-for-an-ssh-key}

{{site.data.keyword.cloud}} コンソールに [SSH 鍵を追加](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)したら、鍵の詳細を編集することができます。 **「ラベル」** (SSH 鍵を容易に識別するために使用されるショート・ネーム) と鍵の**「メモ」**を編集できます。{:shortdesc}

## 始めに
まず、デバイス・メニューに移動して、タスクを完了するための適切なアカウント権限があることを確認します。

* コンソールのデバイス・メニューに移動します。詳しくは、[デバイスへのナビゲート](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)を参照してください。
* 必要なアカウント権限とデバイス・アクセス権限があることを確認します。アカウントの所有者、またはクラシック・インフラストラクチャーの**「ユーザーの管理」**権限を持つユーザーのみが権限を調整できます。

権限について詳しくは、[クラシック・インフラストラクチャーの権限](/docs/iam?topic=iam-infrapermission#infrapermission)および[デバイス・アクセス権限の管理](/docs/vsi?topic=virtual-servers-managing-device-access)を参照してください。

## SSH 鍵の詳細の編集

鍵自体を編集する必要がある場合は、鍵を削除し、正しい鍵を {{site.data.keyword.cloud_notm}} コンソールに追加してください。 SSH 鍵の詳細とともにリストされている指紋は、鍵自体ではなく、鍵の取り出しに使用される短いバイト・シーケンスです。 指紋は、実際の SSH 鍵を表すものではありません。{:note}

SSH 鍵の詳細を編集するには、以下のステップを実行します。

1. **「デバイス」**メニューから、**「管理」>「SSH 鍵」**を選択します。 
2. **「ラベル」**フィールドまたは**「メモ」**フィールドの任意の場所をクリックして、編集用のフィールドを開きます。
3. 対応するフィールドに更新したテキストを入力します。
4. 画面上の任意の場所をクリックして、追加編集用のフィールドを閉じます。


## 次のステップ

編集された SSH 鍵の詳細は、SSH 鍵リストで即時更新されます。
