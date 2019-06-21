---

copyright:
  years: 2014, 2018
lastupdated: "2018-08-15"

keywords: SSH keys, public-key cryptography, SSH

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Informazioni sulle chiavi SSH
{: #about-ssh-keys}

Le chiavi SSH sono utilizzate dai server SSH per identificare un utente o un dispositivo tramite la crittografia della chiave pubblica. Le chiavi SSH sono formate da una combinazione alfanumerica e sono univoche per il dispositivo a cui sono assegnate. In qualsiasi momento, gli utenti autorizzati possono aggiungere, modificare o eliminare le chiavi SSH utilizzando la console {{site.data.keyword.cloud}}.
{:shortdesc}

Puoi richiedere le chiavi SSH durante il provisioning o tramite un [Ricaricamento SO](/docs/software?topic=software-reloading-the-os#reloading-the-os).

Le chiavi SSH permettono l'accesso a un dispositivo senza l'utilizzo di una password dai client corrispondenti per ogni chiave pubblica che viene implementata nel dispositivo. Con l'aggiunta di una chiave SSH a un dispositivo, il dispositivo a cui è stata fornita la chiave SSH accede al dispositivo con la chiave corrispondente senza l'utilizzo di una password.
