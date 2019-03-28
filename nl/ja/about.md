---

copyright:
  years: 2014, 2018
lastupdated: "2018-08-15"

keywords: SSH keys, public-key cryptography, SSH

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH 鍵について
{: #about-ssh-keys}

SSH 鍵は、公開鍵暗号方式を使用してユーザーまたはデバイスを識別するために SSH サーバーによって使用されます。 SSH 鍵は、英数字の組み合わせで構成されており、それらが割り当てられているデバイスに固有です。 許可ユーザーはいつでも、{{site.data.keyword.slportal_full}} を使用して SSH 鍵を追加、編集、または削除できます。

SSH 鍵は、プロビジョン中または[OS 再ロード](/docs/infrastructure/software?topic=software-reloading-the-os)中に要求できます。


SSH 鍵は、デバイスで実装されている各公開鍵の、対応クライアントのパスワードを使用せずにデバイスへのアクセスを許可します。 SSH 鍵をデバイスに追加することにより、SSH 鍵を提供されたデバイスは、パスワードを使用せずに、対応する鍵のデバイスにアクセスします。
