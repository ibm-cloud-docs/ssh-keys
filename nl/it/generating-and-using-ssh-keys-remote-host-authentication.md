---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, remote host authentication SSH keys, public-key cryptography

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Generazione e utilizzo delle chiavi SSH per l'autenticazione host remota
{: #generating-and-using-ssh-keys-for-remote-host-authentication}

Le chiavi sono un modo per identificare te stesso in un server SSH che utilizza la crittografia della chiave pubblica e l'autenticazione di verifica/risposta. Un vantaggio immediato di questo metodo rispetto all'autenticazione tramite password tradizionale è che puoi essere autenticato dal server senza inviare la tua password nella rete. Puoi anche utilizzarlo in modo automatizzato perché consente la comunicazione server in modalità non presidiata.

## Generazione delle chiavi SSH su Linux

Per generare una chiave SSH sul tuo server Linux, esegui il comando `ssh-keygen`. Il comando può richiedere degli indicatori se vuoi personalizzare il tipo di chiave che viene generato così come la firma degli algoritmi utilizzati per generare la chiave. Questo esempio genera una chiave RSA a 2048 bit standard senza una passphrase. Il comando ti richiede l'ubicazione di archiviazione della chiave (il valore predefinito è $HOME/.ssh/) così come una passphrase per proteggere la chiave SSH.

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

## Copia della chiave pubblica sugli host remoti

Per l'autenticazione con un host remoto utilizzando la tua chiave SSH pubblica dovrai utilizzare il comando `ssh-copy-id`. Utilizza l'indicatore `-i` per specificare la chiave pubblica da copiare nell'host remoto.

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

***Nota:*** il comando ssh-copy-id aggiunge le chiavi al file .ssh/authorized_key dell'host remoto.

## Verifica che la chiave è stata copiata correttamente

Per verificare che la chiave pubblica sia stata copiata correttamente nell'host remoto, esegui semplicemente ssh all'host remoto.

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

Come puoi vedere, non viene richiesta la password quando utilizzi ssh-ing nell'host remoto.

## Chiavi SSH con una passphrase

Fornire una passphrase per la tua chiave SSH, fornisce un livello di sicurezza aggiuntivo, ma può anche causare problemi quando stai tentando di eseguire gli script automatizzati che richiedono l'utilizzo della chiave protetta.

ssh-agent può gestire le tue chiavi per te. Immetti la passphrase una volta. ssh-agent conserva la tua chiave nella sua memoria e la trasmette quando necessario. Per permettere a ssh-agent di gestire le tue chiavi immetti il seguente comando:

    eval $(ssh-agent)

Dopo l'avvio del programma utilizzando il comando ssh-add per aggiungere la tua chiave pubblica all'agent, il programma di utilità ssh-add ricerca i nomi della chiave predefiniti, di cui fa parte id_rsa e li aggiunge a ssh-agent. Dopo che hai immesso la tua password, la chiave "sbloccata" viene archiviata con ssh-agent e può essere utilizzata per l'autenticazione con altri server.

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

Ogni volta che apri una nuova sessione del terminale ti sarà richiesta la passphrase delle chiavi. Considera di immettere i seguenti comandi per aggiungere il tuo file `.bash_profile` in modo che ssh-agent si avvii con ogni sessione bash  e che la tua chiave venga aggiunta.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
