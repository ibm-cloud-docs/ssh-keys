---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurazione di SSH per l'ascolto solo su una rete privata
{: #configuring-ssh-to-listen-only-on-a-private-network}

Puoi proteggere ulteriormente il tuo server eseguendo SSHd solo su una rete di backend. Pertanto, devi collegarti alla VPN ogni volta che hai bisogno di accedere a SSH.

1. Individua il seguente file. Utilizza questo file per definire l'indirizzo IP per `sshd`.
```
# nano /etc/ssh/sshd_config
```

2. Individua la riga contenente `ListenAddress 0.0.0.0`. Se inizia con un carattere '#', rimuovilo. Imposta l'indirizzo IP sull'IP su cui desideri sia in ascolto. Puoi trovare il tuo indirizzo IP interno selezionando *Hardware* da {{site.data.keyword.slportal_full}}.
3. Dopo aver effettuato la modifica, riavvia il servizio SSH:
```
# service sshd restart
```

La tua finestra shell corrente non di disconnetterà quando riavvii il servizio. Verifica di poterti collegare al server tramite la nuova porta SSH prima di uscire dalla tua finestra shell corrente. Se si verifica un problema, SSHd non riesce a riavviarsi e devi collegarti al server utilizzando un metodo alternativo.
