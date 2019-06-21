---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: list of group name patterns, SSH access, error messages

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Concessione dell'accesso SSH a un utente
{: #granting-ssh-access-to-a-user}

Segui questa procedura per concedere l'accesso SSH a uno o più utenti. Questa procedura illustra come configurare questo file:

1. Individua il seguente file OpenSSH:
```
/etc/ssh/sshd_config
```

2. Esegui un backup di questo file in modo da poterlo ripristinare se necessario. Ad esempio:
```
cp /etc/ssh/sshd_config{,.'date +%s'}
```

3. Modifica il file utilizzando le parole chiave OpenSSH.


## Parole chiave OpenSSH

### AllowGroups

Dopo questa parola chiave, includi un elenco di modelli del nome del gruppo. Separa i modelli con gli spazi. Se specifichi **Login**, viene consentito solo agli utenti il cui elenco di gruppi supplementari o primari corrisponde a uno dei modelli. Puoi utilizzare `"*" e "?"` come caratteri jolly nei modelli. Sono validi solo i nomi del gruppo; un ID del gruppo numerico non viene riconosciuto. Per impostazione predefinita, **Login** non è consentito per tutti i gruppi.

### AllowUsers

Dopo questa parola chiave, includi un elenco di modelli del nome utente. Separa i modelli con gli spazi. Se specifichi **Login**, viene consentito solo ai nomi utente che corrispondono a uno dei modelli. Puoi utilizzare `"*" e "?"` come caratteri jolly nei modelli. Sono validi solo i nomi utente; un ID utente numerico non viene riconosciuto. Per impostazione predefinita, **Login** non è consentito per tutti gli utenti. Se il modello prende il formato USER@HOST, USER e HOST vengono controllati separatamente, limitando gli accessi a utenti particolari da host particolari.

### DenyGroups

Dopo questa parola chiave, includi un elenco di modelli del nome del gruppo. Separa i modelli con gli spazi. Se specifichi **Login**, non viene consentito agli utenti il cui elenco di gruppi supplementari o primari corrisponde a uno dei modelli. Puoi utilizzare `"*" e "?"` come caratteri jolly nei modelli. Sono validi solo i nomi del gruppo; un ID del gruppo numerico non viene riconosciuto. Per impostazione predefinita, **Login** non è consentito per tutti i gruppi.

### DenyUsers

Dopo questa parola chiave, includi un elenco di modelli del nome utente. Separa i modelli con gli spazi. Se specifichi **Login**, non viene consentito ai nomi utente che corrispondono a uno dei modelli. Puoi utilizzare `"*" e "?"` come caratteri jolly nei modelli. Sono validi solo i nomi utente; un ID utente numerico non viene riconosciuto. Per impostazione predefinita, **Login** non è consentito per tutti gli utenti.  Se il modello prende il formato USER@HOST, USER e HOST vengono controllati separatamente, limitando gli accessi a utenti particolari da host particolari.

## Esempio

Nel seguente esempio, solo a due utenti specifici, `admin` e `user1` è consentito accedere al server.
**Nota:** puoi utilizzare un metodo simile per negare ai gruppi di utilizzare le parole chiave `DenyGroups` e `DenyUsers`.
```
AllowUsers admin user1
```

Per preparare una futura espansione degli utenti, puoi creare un gruppo sul server che può accedere al server. Puoi aggiungere singoli utenti secondo necessità (sostituisci *`username`* con l'utente effettivo):

1. Nella shell, aggiungi un gruppo di utenti, come ad esempio sshusers:
```
groupadd –r sshusers
```

2. Nella shell, aggiungi gli utenti al gruppo:
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. Nel file sshd_config, fornisci l'accesso al gruppo sshusers:
```
AllowGroups sshusers
```

4. Verifica che sshd legga la nuova configurazione senza interruzioni:
```
/usr/sbin/sshd –t
```

```
echo $?
```

  Se ricevi uno `0` che segue il comando `echo $?`, la nuova configurazione è corretta.

  Puoi anche ricevere dei messaggi di errore simili ai seguenti esempi:
```
sshd_config: line 112: Bad configuration option: allowuser
```

```
sshd_config: terminating, 1 bad configuration options
```

5. Dopo che hai corretto tutti gli errori e disponi di una configurazione funzionante, riavvia sshd. Il seguente è un comando di esempio in un sistema compatibile sysv:
  /etc/init.d/sshd restart

Assicurati di creare una nuova sessione SSH senza disconnettere la tua sessione esistente. Verifica di poter eseguire tutte le azioni con gli utenti che hai aggiunto.
