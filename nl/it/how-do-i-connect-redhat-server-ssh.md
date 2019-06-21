---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: RedHat server, main IP address of your server, default options

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connessione a un server RedHat con SSH
{: #connecting-to-a-redhat-server-with-ssh}

Per completare questa procedura, hai bisogno di un client SSH, come PuTTY, sul tuo computer. PuTTY è un client SSH gratuito, ampiamente distribuito.
Nella maggior parte dei casi, puoi utilizzare le opzioni predefinite in PuTTY per connetterti correttamente al tuo server RedHat per la prima volta.

1. Apri PuTTY e immetti l'indirizzo IP principale del tuo server nel campo `'Hostname (or IP address)'` e fai clic su Open.

  La porta predefinita per SSH è la 22, ma puoi modificarla sul server dopo la tua prima connessione riuscita.
  {:note} 
  
2. Il server RedHat ti richiede un nome utente e una password. Immetti le tue informazioni utente/password root per il server.
3. Salva i dettagli della connessione (indirizzo IP e porta) nelle sessioni immettendo l'indirizzo IP e la porta. Crea un titolo per queste proprietà della connessione come ad esempio "My Server" e fai clic su Save.
  Quando ti connetti al tuo server, dovrai solo evidenziare la sessione salvata e fare clic su Open.

Puoi connetterti al tuo server usando la rete pubblica.
Puoi anche connetterti utilizzando la rete privata. Segui le istruzioni nella console {{site.data.keyword.cloud}} per la connessione alla VPN e quindi utilizza SSH per connetterti al tuo indirizzo IP privato.
