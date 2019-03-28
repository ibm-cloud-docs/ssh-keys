---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 非標準ポートで実行するための SSH の構成
{: #configuring-ssh-to-run-on-a-non-standard-port}

SSH を非標準ポートで実行するよう強制するには、以下のステップを実行します。

1. テキスト・エディターで /etc/ssh/sshd_config を開きます。 以下は、vi エディターの例です。
```
# vi /etc/ssh/sshd_config
```

2. 以下の行を参照します。
```
# Port 22
```

3. この行をアンコメントし、新しいポートを反映するように編集します。
```
Port 2255
```
(これは、任意の非標準ポートに設定できます)

4. ファイルを保存して終了し、SSH を再始動します。
```
# /etc/init.d/sshd restart
```

5. ポート 22 で SSH を使用してサーバーに接続している場合、接続は除去され、新しいポートを使用して再接続する必要があります。
