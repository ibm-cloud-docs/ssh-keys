---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Limitazione dell'utente root dall'accesso SSH
{: #restricting-the-root-user-from-ssh-access}

Ogni sistema Linux sulla rete {{site.data.keyword.cloud}} ha un utente root con autorizzazioni amministrative. In Linux, puoi creare i gruppi wheel, che forniscono agli utenti autorizzazioni simili a quelle dell'utente root tramite "sudo" senza il bisogno di utilizzare le credenziali dell'utente root. Dopo che hai creato un gruppo wheel con le autorizzazioni sudo, puoi limitare agli utenti in tale gruppo l'accesso SSH. Limitando gli utenti in questo modo, proteggi il dispositivo da vulnerabilità di sicurezza relative all'accessibilità della rete. Gli utenti che fanno parte del gruppo wheel possono ancora eseguire le funzioni amministrative sul dispositivo in qualsiasi momento.
{:shortdesc}

Segui questa procedura per limitare all'utente root l'accesso SSH.

1. Apri il file 'etc/group' e controlla se contiene una riga che definisce un gruppo wheel:
```
wheel:x:10:root
```

    Se questa riga non è nel file, creala.

2. Aggiungi almeno un utente alla riga del gruppo wheel:
```
wheel:x:10:root, user1
```

    Gli utenti aggiunti al gruppo wheel hanno le stesse autorizzazioni dell'utente root, ma utilizzano i propri nomi utente univoci quando accedono al sistema.
3. Esegui il comando `:wq` per salvare le modifiche e uscire dal file.
4. Apri `/etc/ssh/sshd_config`.
5. Modifica la riga `PermitRootLogin yes` in modo che legga `PermitRootLogin no`.
6. Esegui il comando `:wq` per salvare le modifiche e uscire dal file.
7. Immetti `visudo` nella **Command Line** per generare le autorizzazioni del comando.
8. Rimuovi **hash (#)** dalla seguente riga per annullare il comment della riga:
```
# %wheel ALL=(ALL) ALL
```

    **Nota:** l'annullare il comment di questa riga consente agli utenti nel gruppo wheel di eseguire tutti i comandi.

9. Esegui il comando `:wq` per salvare le modifiche e uscire dal file.
10. Immetti il seguente comando nella riga di comando:
```
vi /etc/pam.d/su
```

11. Rimuovi **hash (#)** dalla seguente riga per annullare il comment della riga:
```
#auth required pam_wheel.so use_uid
```

    **Nota:** l'annullare il comment di questa riga richiede agli utenti di far parte del gruppo wheel per avere le autorizzazioni per eseguire tutti i comandi.
12. Esegui il comando `:wq` per salvare le modifiche e uscire dal file.
13. Immetti il seguente comando per salvare tutte le modifiche e riavviare SSH:
```
# etc/init.d/ssh restart
```

## Passi successivi

Dopo aver limitato all'utente root l'accesso SSH, l'utente root non può accedere a SSH. Se un utente al momento può accedere al server tramite SSH nell'utente root, la connessione avrà esito negativo dopo il riavvio di SSH nella procedura precedente. Tutti i tentativi futuri di collegarsi a SSH tramite l'utente root hanno esito negativo. Per annullare queste modifiche, ripetere le istruzioni e riportare `PermitRootLogin` no su `PermitRootLogin` yes.
