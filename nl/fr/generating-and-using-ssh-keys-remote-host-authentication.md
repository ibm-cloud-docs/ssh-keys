---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Génération et utilisation de clés SSH pour l'authentification d'hôte distant

Les clés SSH constituent un moyen de vous identifier sur un hôte SSH qui utilise un système de chiffrement à clé publique et de réponse d'identification. L'avantage immédiat de cette méthode par rapport à l'authentification classique par mot de passe est la possibilité de vous faire authentifier par le serveur sans envoyer votre mot de passe sur le réseau. Vous pouvez également l'utiliser avec l'automatisation car cette méthode permet la communication avec des serveurs automatisés.

## Génération de clés SSH sur Linux

Pour générer une clé SSH sur votre serveur Linux, exécutez la commande `ssh-keygen`. La commande accepte les indicateurs si vous voulez personnaliser le type de clé générée ainsi que les algorithmes de signature utilisés pour générer la clé. Voici un exemple de clé RSA 2048 bits standard sans phrase passe. La commande vous demande l'emplacement de stockage de la clé ($HOME/.ssh/ par défaut) ainsi qu'une phrase passe pour sécuriser la clé SSH.

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

## Copie de la clé publique sur des hôtes distants

Pour s'authentifier avec un hôte distant à l'aide de votre clé SSH publique, vous utiliserez la commande `ssh-copy-id`. Utilisez l'indicateur `-i` pour spécifier la clé publique à copier sur l'hôte distant.

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

***Remarque :*** La commande ssh-copy-id ajoute les clés dans le fichier .ssh/authorized_key de l'hôte distant.

## Test de copie de la clé

Pour tester si la clé publique a été copiée correctement sur l'hôte distant, connectez-vous à l'hôte distant avec ssh.

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

Comme vous pouvez le constater, aucun mot de passe n'a été demandé lors de cette connexion SSH à l'hôte distant.

## Clés SSH avec phrase passe

La fourniture d'une phrase passe pour votre clé SSH offre une couche de sécurité supplémentaire, mais elle peut également causer des problèmes lorsque vous essayez d'exécuter des scripts automatiques nécessitant l'utilisation de la clé protégée. 

L'agent SSH (ssh-agent) peut gérer les clés à votre place. Vous n'entrez qu'une seule fois la phrase passe. L'agent ssh-agent conserve votre clé en mémoire et la restitue si nécessaire. Pour que l'agent ssh-agent gère vos clés, exécutez la commande suivante :

    eval $(ssh-agent)

Lorsque le programme utilise la commande ssh-add pour ajouter votre clé publique à l'agent, l'utilitaire ssh-add recherche les noms de clés par défaut, parmi lesquels figure id_rsa, et les ajoute dans l'agent ssh-agent. Après avoir entré votre mot de passe, la clé "déverrouillée" est stockée avec ssh-agent et peut être utilisée pour s'authentifier auprès d'autres serveurs.

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

Chaque fois que vous ouvrez une nouvelle session de terminal, vous serez invité à saisir la phrase passe de la clé. Pensez à exécuter les commandes suivantes pour ajouter le fichier `.bash_profile` de sorte que l'agent ssh-agent démarre avec toutes les sessions bash et que votre clé soit ajoutée.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
