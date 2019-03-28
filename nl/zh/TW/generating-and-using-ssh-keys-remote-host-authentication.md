---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, remote host authentication SSH keys, public-key cryptography

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 產生及使用 SSH 金鑰來進行遠端主機鑑別
{: #generating-and-using-ssh-keys-for-remote-host-authentication}

SSH 金鑰可以用來向使用公開金鑰加密法和盤查-回應鑑別的 SSH 伺服器識別您自己。此方法相較於傳統密碼鑑別的立即優點，是您可以由伺服器鑑別而不必在網路上傳送密碼。您也可以自動地使用它，因為它允許自動式伺服器通訊。

## 在 Linux 上產生 SSH 金鑰

若要在您的 Linux 伺服器上產生 SSH 金鑰，請執行指令 `ssh-keygen`。如果您想要自訂所產生金鑰的類型，以及用來產生金鑰的簽署演算法，指令可以接受旗標。此範例會產生不含通行詞組的標準 2048 位元 RSA 金鑰。指令會提示您輸入儲存金鑰的位置（預設值為 $HOME/.ssh/）以及保護 SSH 金鑰用的通行詞組。

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

## 將公開金鑰複製到遠端主機

若要使用您的公用 SSH 金鑰向遠端主機進行鑑別，請使用 `ssh-copy-id` 指令。使用 `-i` 旗標可指定要複製到遠端主機的公開金鑰。

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

***附註：***ssh-copy-id 指令會將金鑰附加到遠端主機的 .ssh/authorized_key 檔案。

## 測試金鑰是否已正確地複製

若要測試公開金鑰是否已適當地複製到遠端主機，只需要以 ssh 連接到遠端主機。

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

如您所見，以 ssh 連接到遠端主機時不會提示輸入密碼。

## 具有通行詞組的 SSH 金鑰

為您的 SSH 金鑰提供通行詞組，可以額外提供一層安全，但它也可能在您嘗試執行需要使用受保護金鑰的自動化 Script 時導致問題。

ssh-agent 可以為您管理金鑰。您只要輸入一次通行詞組。ssh-agent 會將您的金鑰保存在它的記憶體中，並在需要時取出它。若要讓 ssh-agent 管理您的金鑰，請發出下列指令：

    eval $(ssh-agent)

程式開始使用 ssh-add 指令將您的公開金鑰新增至代理程式之後，ssh-add 公用程式會搜尋預設金鑰名稱（其 id_rsa 為一），並將它們新增至 ssh-agent。鍵入密碼之後，「解除鎖定」的金鑰會與 ssh-agent 一起儲存，並且可以用來向其他伺服器進行鑑別。

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

您每次開啟新的終端機階段作業時，都會提示您輸入金鑰通行詞組。請考慮執行下列指令以附加您的 `.bash_profile` 檔，讓每個 bash 階段作業都會啟動 ssh-agent，且新增您的金鑰。

    echo 'eval $(ssh-agent)' >> ~/.bash_profile
    echo 'ssh-add' >> ~/.bash_profile
