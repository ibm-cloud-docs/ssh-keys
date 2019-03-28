---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, remote host authentication SSH keys, public-key cryptography

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# リモート・ホスト認証のための SSH 鍵の生成および使用
{: #generating-and-using-ssh-keys-for-remote-host-authentication}

SSH 鍵は、公開鍵暗号方式およびチャレンジ応答認証を使用する SSH サーバーに対してユーザー自身を識別する方法です。 従来型のパスワード認証と比べた場合のこの方式の直接の利点は、ネットワークでパスワードを送信せずにサーバーで認証が行える点です。 また、この方式では無人サーバー通信が可能なため、自動化で使用することができます。

## Linux での SSH 鍵の生成

Linux サーバー上で SSH 鍵を生成するには、コマンド `ssh-keygen` を実行します。 生成される鍵のタイプ、および鍵の生成に使用される署名アルゴリズムをカスタマイズしたい場合、このコマンドはフラグを取ることができます。 以下の例は、パスフレーズのない標準の 2048 ビット RSA 鍵を生成します。 このコマンドでは、鍵の保管場所 (デフォルトは $HOME/.ssh/)、および SSH 鍵を保護するためのパスフレーズの入力を求めるプロンプトが出されます。

    root@bck2:/etc# ssh-keygen
    Generating public/private rsa key pair.
    Enter file in which to save the key (/root/.ssh/id_rsa):
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in /root/.ssh/id_rsa.
    Your public key has been saved in /root/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx root@bck2.example.com
    The key's randomart image is:
    +---[RSA 2048]----+
    |.  oo*%=+o..     |
    |.++.oX+=. .      |
    |..+ooo=. .       |
    |   E.+. .o.      |
    |    +   S..+     |
    |     . +. =      |
    |      o  = o     |
    |      .o+ +      |
    |       +o.       |
    +----[SHA256]-----+

## リモート・ホストへの公開鍵のコピー

公開 SSH 鍵を使用してリモート・ホストでの認証を行うには、`ssh-copy-id` コマンドを使用します。 `-i` フラグを使用して、リモート・ホストにコピーする公開鍵を指定します。

    root@bck2: # ssh-copy-id -i /root/.ssh/id_rsa.pub root@10.176.18.15
    /usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/root/.ssh/id_rsa.pub"
    The authenticity of host '10.176.18.15 (10.176.18.15)' can't be established.
    ECDSA key fingerprint is SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.

    Are you sure you want to continue connecting (yes/no)? yes
    /usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
    /usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
    root@10.176.18.15's password:

    Number of key(s) added: 1

    Now try logging into the machine, with:   "ssh 'root@10.176.18.15'"
    and check to make sure that only the key(s) you wanted were added.

***注:*** ssh-copy-id コマンドは、リモート・ホストの .ssh/authorized_key ファイルに鍵を追加します。

## 鍵が正しくコピーされたことのテスト

公開鍵がリモート・ホストに正しくコピーされたことをテストするには、単純にリモート・ホストに ssh を実行します。

    root@bck2:/etc# ssh root@10.176.18.15
    Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * Documentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/advantage

      Get cloud support with Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

ご覧のように、リモート・ホストへの ssh を実行しているとき、パスワードの入力を要求するプロンプトは出されません。

## パスフレーズ付きの SSH 鍵

SSH 鍵のパスフレーズを指定すると追加のセキュリティー層が提供されますが、保護された鍵の使用を必要とする自動スクリプトを実行しようとしているときに問題が発生する可能性があります。

ssh-agent は、ユーザーの代わりに鍵を管理できます。 ユーザーはパスフレーズを 1 回入力します。 ssh-agent はメモリー内に鍵を保持し、必要なときに取り出します。 ssh-agent で鍵の管理を行うには、以下のコマンドを実行します。

    eval $(ssh-agent)

プログラムが ssh-add コマンドの使用を開始して公開鍵をエージェントに追加すると、ssh-add ユーティリティーはデフォルト鍵名 (id_rsa はそのうちのひとつ) を検索し、それらを ssh-agent に追加します。 パスワードを入力すると、「アンロックされた」鍵が ssh-agent に保管され、他のサーバーでの認証に使用できます。

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

新規端末セッションを開く度に、鍵のパスフレーズの入力を要求するプロンプトが出されます。 すべての bash セッションで ssh-agent が開始され、鍵が追加されるように、以下のコマンドを実行して `.bash_profile` ファイルを追加することを検討してください。

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
