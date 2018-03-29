---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Gerando e usando chaves SSH para autenticação de host remoto

As chaves SSH são uma maneira de identificar se um servidor SSH usa criptografia de chave pública e
autenticação de resposta de segurança. Uma vantagem imediata desse método sobre a autenticação de senha
tradicional é a possibilidade de ser autenticado pelo servidor sem enviar sua senha pela rede. Esse método também
pode ser usado com automação, pois permite uma comunicação do servidor não assistida.

## Gerando chaves SSH no Linux

Para gerar uma chave SSH em seu servidor Linux, execute o comando `ssh-keygen`. O
comando pode usar sinalizações, caso deseje customizar o tipo de chave que é gerada, bem como os
algoritmos de assinatura usados para gerar a chave. Este exemplo gera uma chave RSA de 2.048 bits padrão sem
uma passphrase. O comando solicita o local para armazenar a chave (o padrão é $HOME/.ssh/), bem como uma
passphrase para proteger a chave SSH.

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

## Copiando a chave pública para hosts remotos

Para autenticar-se com um host remoto usando sua chave SSH pública, você usará o
comando `ssh-copy-id`. Use a sinalização `-i` para especificar a
chave pública para copiá-la para o host remoto.

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

***Nota:*** o comando ssh-copy-id anexa as chaves ao arquivo
.ssh/authorized_key do host remoto.

## Testando se a chave foi copiada corretamente

Para testar se a chave pública foi copiada corretamente para o host remoto, simplesmente execute ssh no
host remoto.

    root@bck2:/etc# ssh root@10.176.18.15
    Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * Documentação:  https://help.ubuntu.com
    * Gerenciamento:     https://landscape.canonical.com
    * Suporte:        https://ubuntu.com/advantage

      Get cloud support with Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

Como pode ver, nenhum prompt para a senha é exibido ao executar ssh no host remoto.

## Chaves SSH com uma passphrase

O fornecimento de uma passphrase para sua chave SSH fornece uma camada adicional de segurança, mas também
pode causar problemas quando você está tentando executar scripts automatizados que requerem o uso da chave
protegida. 

O ssh-agent pode gerenciar suas chaves para você. Insira a passphrase uma vez. O ssh-agent mantém sua
chave em sua memória e a obtém quando necessário. Para que o ssh-agent gerencie suas chaves, emita o comando a
seguir:

    eval $(ssh-agent)

Após o programa iniciar o uso do comando ssh-add para incluir sua chave pública no agente, o
utilitário ssh-add procura por keynames padrão, cujo id_rsa é um, e os inclui no ssh-agent. Após digitar sua
senha, a chave "unlocked" é armazenada com o ssh-agent e poderá ser usada para autenticar-se em outros
servidores.

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

Cada vez que você abre uma nova sessão de terminal, a passphrase das chaves é solicitada. Considere
executar os comandos a seguir para anexar seu arquivo `.bash_profile` para que
o ssh-agent inicie com cada sessão bash e sua chave é incluída.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
