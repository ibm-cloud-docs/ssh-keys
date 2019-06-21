---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Aggiunta di una chiave SSH
{: #adding-an-ssh-key}

Puoi aggiungere le chiavi SSH al tuo account se sei un utente autorizzato. Ogni account può avere fino a 100 chiavi SSH in qualsiasi momento. Le chiavi SSH vengono spesso utilizzate nel [processo di ricaricamento del SO](/docs/software?topic=software-reloading-the-os#reloading-the-os) e possono essere utilizzate anche quando esegui il provisioning di un nuovo dispositivo.
{:shortdesc}

## Prima di iniziare
Innanzitutto, genera la tua chiave SSH pubblica, passa al menu del dispositivo e assicurati di disporre delle autorizzazioni di account corrette per completare le attività.

* [Genera la chiave SSH pubblica ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://help.github.com/articles/generating-ssh-keys){: new_window} per il tuo dispositivo.
* Passa al menu del dispositivo della tua console. Per ulteriori informazioni, vedi [Passaggio ai dispositivi](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Assicurati di disporre di tutte le autorizzazioni di account necessarie e dell'accesso al dispositivo. Solo il proprietario dell'account o un utente con l'autorizzazione di **Gestione utenti** dell'infrastruttura classica può modificare le autorizzazioni.

Per ulteriori informazioni sulle autorizzazioni, vedi [Autorizzazioni dell'infrastruttura classica](/docs/iam?topic=iam-infrapermission#infrapermission) e [Gestione dell'accesso al dispositivo](/docs/vsi?topic=virtual-servers-managing-device-access).

## Aggiunta di una chiave SSH al tuo account
Per aggiungere una chiave SSH al tuo account, completa la seguente procedura.

1. Dal menu **Devices**, seleziona **Manage > SSH Keys**.
2. Fai clic su **Add**.
3. Fai clic su **Browse** per trovare il file della chiave pubblica o immettilo manualmente nella casella di testo **Key Contents**.
4. Immetti un **nome breve** per la chiave SSH nel campo **Label**.
5. Immetti tutte le note applicabili nel campo **Notes**, se necessario.
6. Fai clic su **Add** per aggiungere la chiave SSH. 

## Passi successivi

Dopo aver aggiunto la chiave SSH, questa viene visualizzata nell'elenco delle chiavi SSH. Puoi [modificare i dettagli della chiave](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key) in qualsiasi momento. Puoi anche [rimuovere la chiave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key) dall'elenco. Rimuovi le chiavi SSH obsolete il prima possibile per garantire che lo spazio sia sufficiente se hai bisogno di aggiungere ulteriori chiavi.
