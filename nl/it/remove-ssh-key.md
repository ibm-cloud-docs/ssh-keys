---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Rimozione di una chiave SSH
{: #removing-an-ssh-key}

Quando una chiave SSH archiviata nella console {{site.data.keyword.cloud}} diventa obsoleta o non è più necessaria, puoi rimuoverla. Rimuovi le chiavi SSH obsolete il prima possibile per garantire che ci sia abbastanza spazio per ulteriori chiavi valide.
{:shortdesc}

## Prima di iniziare
Innanzitutto, passa al menu del dispositivo e assicurati di disporre delle autorizzazioni di account corrette per completare le attività.

* Passa al menu del dispositivo della tua console. Per ulteriori informazioni, vedi [Passaggio ai dispositivi](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Assicurati di disporre di tutte le autorizzazioni di account necessarie e dell'accesso al dispositivo. Solo il proprietario dell'account o un utente con l'autorizzazione di **Gestione utenti** dell'infrastruttura classica può modificare le autorizzazioni.

Per ulteriori informazioni sulle autorizzazioni, vedi [Autorizzazioni dell'infrastruttura classica](/docs/iam?topic=iam-infrapermission#infrapermission) e [Gestione dell'accesso al dispositivo](/docs/vsi?topic=virtual-servers-managing-device-access).

## Rimozione di una chiave SSH

1. Dal menu **Devices**, seleziona **Manage > SSH Keys**.
2. Fai clic sull'icona **Remove** accanto alla chiave SSH che desideri rimuovere.
3. Fai clic su **Yes** per confermare. 

## Passi successivi

Dopo che hai rimosso una chiave SSH, viene immediatamente rimossa dall'elenco. La chiave non può più essere utilizzata quando esegui il provisioning di un nuovo dispositivo o quando esegui un ricaricamento SO su un dispositivo esistente. Se la chiave viene rimossa per errore o deve essere aggiunta nuovamente alla console {{site.data.keyword.cloud_notm}}, vedi [Aggiunta di una chiave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key).
