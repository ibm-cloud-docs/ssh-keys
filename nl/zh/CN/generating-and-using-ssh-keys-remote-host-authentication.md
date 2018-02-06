---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 针对远程主机认证生成并使用 SSH 密钥

SSH 密钥是一种用于向使用公用密钥密码术和提问应答认证的 SSH 服务器进行自身识别的方式。跟传统的密码认证相比，此方法的显著优势在于无需通过网络发送密码即可由服务器进行认证。此外，因为它支持无人照管的服务器通信，所以还可以实现自动化。

## 在 Linux 上生成 SSH 密钥

要在 Linux 服务器上生成 SSH 密钥，请运行命令 `ssh-keygen`。如果您想要定制生成的密钥类型以及用于生成密钥的签名算法，那么此命令可以带标记。此示例会生成没有口令的标准 2048 位 RSA 密钥。此命令会提示您选择存储密钥的位置（缺省位置为 $HOME/.ssh/）以及确保 SSH 密钥安全的口令。

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

## 将公用密钥复制到远程主机

要使用公用 SSH 密钥向远程主机进行认证，需使用 `ssh-copy-id` 命令。使用 `-i` 标记来指定要复制到远程主机的公用密钥。

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

***注：***ssh-copy-id 命令会将密钥附加到远程主机的 .ssh/authorized_key 文件。

## 测试是否已正确复制密钥

要测试是否将公用密钥正确复制到了远程主机，只需 ssh 到远程主机即可。

    root@bck2:/etc# ssh root@10.176.18.15
    Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * 文档： https://help.ubuntu.com
    * 管理： https://landscape.canonical.com
    * 支持： https://ubuntu.com/advantage

      Get cloud support with Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

如您所见，在 ssh 到远程主机时并未提示输入密码。

## 带口令的 SSH 密钥

通过为 SSH 密钥提供口令可以提供多一层安全保护，但在尝试运行需要使用受保护密钥的自动脚本时，也可能会导致问题。 

ssh-agent 可以为您管理密钥。您输入口令一次。ssh-agent 会将密钥保存在内存中，并在需要时将其拉出。要让 ssh-agent 管理密钥，请发出以下命令：

    eval $(ssh-agent)

当程序开始使用 ssh-add 命令将公用密钥添加到代理程序之后，ssh-add 实用程序会搜索缺省的密钥名（id_rsa 是其中之一），然后将它们都添加到 ssh-agent 中。在您输入密码之后，会使用 ssh-agent 存储“已解锁的”密钥，并可在针对其他服务器进行认证时使用该密钥。

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

每次打开新的终端会话时，都会提示您输入密钥口令。可以考虑运行以下命令以附加 `.bash_profile` 文件，这样 ssh-agent 会随每个 Bash 会话启动，并会添加您的密钥。

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
