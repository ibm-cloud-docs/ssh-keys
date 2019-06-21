---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH keys, SSH key, device-specific

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# Domande frequenti (FAQ): chiavi SSH
{: #faqs-ssh-keys}

## Dove posso trovare la mia chiave SSH?
{:faq}

Le chiavi SSH sono specifiche per il dispositivo e si trovano all'interno di esso. Poiché ogni sistema operativo è differente, i passi per individuare la chiave SSH sono specifici per SO. Per ulteriori informazioni sulla generazione di una chiave SSH, fai riferimento all'articolo di GitHub in [generating SSH keys ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window}.

## Quante chiavi SSH posso aggiungere al mio account?
{:faq}

Puoi associare fino a 100 chiavi SSH al tuo account. Gli utenti autorizzati possono [aggiungere 1 chiave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key) alla volta utilizzando la console {{site.data.keyword.cloud}}. Visto che la maggior parte degli utenti non ha bisogno di 100 chiavi, puoi rimuovere tutte la chiavi di cui non hai bisogno per assicurarti che lo spazio sia disponibile per ulteriori chiavi valide. Per ulteriori informazioni, consulta [rimozione di chiavi SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key).

## Non vedo elencata la mia chiave SSH corrente, ma vedo un'impronta digitale. Cosa è?
{:faq}

L'impronta digitale che viene visualizzata con i dettagli di una chiave SSH è una sequenza abbreviata di byte generati dal sistema. L'impronta digitale è più breve della chiave SSH stessa e viene utilizzata per l'autenticazione o la ricerca della chiave pubblica per il dispositivo associato.

## Se creo o ricarico un dispositivo che utilizza un template dell'immagine, le chiavi SSH saranno trasportate?
{:faq}

Sì e no. Ogni dispositivo ha una chiave SSH univoca, per cui la chiave per il dispositivo appena fornito o ricaricato sarà differente da quella dell'immagine.  Tuttavia, le chiavi SSH associate a un'immagine Flex o a un template dell'immagine standard sono associate al dispositivo quando ne viene eseguito il provisioning o viene ricaricato. Puoi inoltre aggiungere le chiavi durante il processo di configurazione.
