---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH key, key details, IBM Cloud infrastructure customer

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Modifica dei dettagli di una chiave SSH
{: #editing-details-for-an-ssh-key}

Dopo aver [aggiunto una chiave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key) nella console {{site.data.keyword.cloud}}, puoi modificare i dettagli della chiave. Puoi modificare **Label** (il nome breve che viene utilizzato per identificare facilmente la chiave SSH) e **Notes** della chiave.
{:shortdesc}

## Prima di iniziare
Innanzitutto, passa al menu del dispositivo e assicurati di disporre delle autorizzazioni di account corrette per completare le attività.

* Passa al menu del dispositivo della tua console. Per ulteriori informazioni, vedi [Passaggio ai dispositivi](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Assicurati di disporre di tutte le autorizzazioni di account necessarie e dell'accesso al dispositivo. Solo il proprietario dell'account o un utente con l'autorizzazione di **Gestione utenti** dell'infrastruttura classica può modificare le autorizzazioni.

Per ulteriori informazioni sulle autorizzazioni, vedi [Autorizzazioni dell'infrastruttura classica](/docs/iam?topic=iam-infrapermission#infrapermission) e [Gestione dell'accesso al dispositivo](/docs/vsi?topic=virtual-servers-managing-device-access).

## Modifica dei dettagli della chiave SSH

Se hai bisogno di modificare la chiave stessa, rimuovila e aggiungi la chiave corretta alla console {{site.data.keyword.cloud_notm}}. L'impronta digitale che viene elencata con i dettagli della chiave SSH non è la chiave stessa; è una breve sequenza di byte utilizzati nel recupero della chiave. L'impronta digitale potrebbe non rappresentare la chiave SSH attuale in alcun modo. 
{:note}

Per modificare i dettagli della chiave SSH, completa la seguente procedura.

1. Dal menu **Devices**, seleziona **Manage > SSH Keys**. 
2. Fai clic in un qualsiasi punto nel campo **Label** o nel campo **Notes** per aprire il campo per la modifica.
3. Immetti il testo aggiornato nel campo corrispondente.
4. Fai clic in un qualsiasi punto nella schermata per chiudere il campo e finire le modifiche.


## Passi successivi

I dettagli della chiave SSH che vengono modificati sono aggiornati immediatamente nell'elenco delle chiavi SSH.
