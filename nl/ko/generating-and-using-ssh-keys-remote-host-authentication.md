---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 원격 호스트 인증을 위한 SSH 키 생성 및 사용

SSH 키는 공개 키 암호 방식 및 인증 확인 응답 인증을 사용하는 SSH 서버에 대해 자체 식별하는 방법입니다. 기존 비밀번호 인증에 비해 이 방법을 사용하면 비밀번호를 네트워크를 통해 보내지 않고 서버에서 인증받을 수 있습니다. 또한 무인 서버 통신이 가능하여 자동화와 함께 이 방법을 사용할 수 있습니다.

## Linux에서 SSH 키 생성

Linux 서버에서 SSH 키를 생성하려면 `ssh-keygen` 명령을 실행하십시오. 키 생성에 사용되는 서명 알고리즘 및 생성된 키 유형을 사용자 정의하려는 경우 명령에서는 플래그를 사용할 수 있습니다. 이 예제는 비밀번호 문구 없이 표준 2048비트 RSA 키를 생성합니다. 이 명령은 SSH 키 보안을 위한 비밀번호 문구 및 키 저장 위치(기본값은 $HOME/.ssh/임)를 묻는 프롬프트를 표시합니다.

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

## 원격 호스트에 공개 키 복사

공개 SSH 키를 사용하여 원격 호스트를 인증하기 위해 `ssh-copy-id` 명령을 사용합니다. 원격 호스트에 복사할 공개 키를 지정하려면 `-i` 플래그를 사용하십시오.

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

***참고:*** ssh-copy-id 명령은 원격 호스트의 .ssh/authorized_key 파일에 키를 추가합니다.

## 키가 올바르게 복사되었는지 테스트

공개 키가 원격 호스트에 올바르게 복사되었는지 테스트하려면 SSH를 통해 원격 호스트에 접속하십시오.

    root@bck2:/etc# ssh root@10.176.18.15
    Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * 문서:  https://help.ubuntu.com
    * 관리:  https://landscape.canonical.com
    * 지원:  https://ubuntu.com/advantage

      Get cloud support with Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

표시된 대로, 원격 호스트에 SSH를 통해 접속하는 경우 비밀번호를 묻는 프롬프트가 없습니다.

## 비밀번호 문구가 있는 SSH 키

SSH 키의 비밀번호 문구가 추가 보안 계층을 제공하는 경우, 보호된 키를 사용해야 하는 자동화된 스크립트를 실행하려고 하면 문제가 발생할 수 있습니다. 

ssh-agent는 사용자 키를 관리할 수 있습니다. 사용자는 비밀번호 문구를 한 번 입력합니다. ssh-agent가 해당 메모리에 이 키를 보관하고 필요한 경우 가져옵니다. ssh-agent가 키를 관리하게 하려면 다음 명령을 실행하십시오.

    eval $(ssh-agent)

프로그램이 ssh-add 명령 사용을 시작하여 에이전트에 공개 키를 추가하면, ssh-add 유틸리티가 기본 키 이름(예: id_rsa)을 검색하고 ssh-agent에 추가합니다. 비밀번호를 입력하면 "잠금 해제된" 키가 ssh-agent를 통해 저장되고 다른 서버에 대해 인증하는 데 사용될 수 있습니다.

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

새 터미널 세션을 열 때마다 키 비밀번호 문구를 묻는 프롬프트가 표시됩니다. ssh-agent가 bash 세션마다 시작되고 키가 추가되도록 `.bash_profile` 파일을 추가하려면 다음 명령 실행을 고려하십시오.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
