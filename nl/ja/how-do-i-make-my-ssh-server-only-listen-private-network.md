---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# プライベート・ネットワークのみで listen するための SSH の構成
{: #configuring-ssh-to-listen-only-on-a-private-network}

バックエンド・ネットワークでのみ SSHd を実行することにより、さらにサーバーを保護することができます。 そのため、SSH へのアクセスが必要になる度に VPN に接続する必要があります。

1. 以下のファイルを見つけます。 このファイルを使用して、`sshd` の IP アドレスを定義します。
```
# nano /etc/ssh/sshd_config
```

2. `ListenAddress 0.0.0.0` が含まれている行を見つけます。 「#」文字で開始されている場合は、この文字を削除してください。 IP アドレスを、listen する IP アドレスに設定します。 内部 IP アドレスは、{{site.data.keyword.cloud}} コンソールから*「ハードウェア」* を選択して見つけることができます。
3. 変更を行ったら、以下のようにして SSH サービスを再始動します。
```
# service sshd restart
```

サービスを再始動するとき、現行のシェル・ウィンドウは切断されません。 現行のシェル・ウィンドウを終了する前に、新しい SSH ポートを使用してサーバーに接続できることを確認してください。 問題があると SSHd は再始動に失敗し、ユーザーは代わりの方法を使用してサーバーに接続する必要があります。
