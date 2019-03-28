---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# root ユーザーの SSH アクセスの制限
{: #restricting-the-root-user-from-ssh-access}

{{site.data.keyword.cloud}} ネットワーク上のすべての Linux システムには、管理権限を持つ root ユーザーがいます。 Linux 内に wheel グループを作成できます。wheel グループは、root ユーザーの資格情報の使用を要求せずに、「sudo」を介して root ユーザーの権限に似た権限をユーザーに提供します。 root の sudo 権限を持つ wheel グループを作成したら、そのグループ内のユーザーの SSH アクセスを制限できます。 このようにユーザーを制限することにより、ネットワークでのアクセスにつきもののセキュリティー脆弱性からデバイスを保護します。 wheel グループに属しているユーザーは、引き続き、いつでもデバイスに対して管理機能を実行できます。
{:shortdesc}

root ユーザーの SSH アクセスを制限するには、以下のステップを実行します。

1. 「etc/group」ファイルを開き、wheel グループを定義する以下の行が含まれているかどうか確認します。
```
wheel:x:10:root
```

    この行がファイルに含まれていない場合は、作成します。

2. 以下のようにして、少なくとも 1 人のユーザーを wheel グループ行に追加します。
```
wheel:x:10:root, user1
```

    wheel グループに追加されたユーザーは、root ユーザーと同一の権限を持ちますが、システムにアクセスするときは固有のユーザー名を使用します。
3. `:wq` コマンドを実行して変更を保存し、ファイルを終了します。
4. `/etc/ssh/sshd_config` を開きます。
5. `PermitRootLogin yes` 行を `PermitRootLogin no` に変更します。
6. `:wq` コマンドを実行して変更を保存し、ファイルを終了します。
7. **コマンド・ライン**に `visudo` と入力してコマンドの権限を生成します。
8. 以下の行から**ハッシュ (#)** を削除し、行をアンコメントします。
```
# %wheel ALL=(ALL) ALL
```

    **注:** この行をアンコメントすると、wheel グループ内のユーザーはすべてのコマンドを実行できます。

9. `:wq` コマンドを実行して変更を保存し、ファイルを終了します。
10. コマンド・ラインで以下のコマンドを実行します。
```
vi /etc/pam.d/su
```

11. 以下の行から**ハッシュ (#)** を削除し、行をアンコメントします。
```
#auth required pam_wheel.so use_uid
```

    **注:** この行をアンコメントするには、ユーザーは wheel グループに所属し、すべてのコマンドを実行する権限を持っている必要があります。
12. `:wq` コマンドを実行して変更を保存し、ファイルを終了します。
13. 以下のコマンドを実行して、すべての変更を保存し、SSH を再始動します。
```
# etc/init.d/ssh restart
```

## 次のステップ

root ユーザーの SSH アクセスを制限した後は、root ユーザーは SSH にログインできません。 ユーザーが現在 root ユーザーとして SSH 経由でサーバーにアクセスできても、前の手順で SSH を再始動した後に接続は失敗します。 root ユーザーを介した SSH への接続試行は、今後すべて失敗します。 これらの変更を元に戻すには、ステップを繰り返し、`PermitRootLogin` no を `PermitRootLogin` yes に変更します。
