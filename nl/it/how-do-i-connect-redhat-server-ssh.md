---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connessione a un server RedHat con SSH

Per completare questa procedura, hai bisogno di un client SSH, come PuTTY, sul tuo computer. PuTTY è un client SSH gratuito, ampiamente distribuito.
In molti casi, puoi utilizzare le opzioni predefinite in PuTTY per collegarti correttamente al tuo server RedHat per la prima volta.

1. Apri PuTTY e immetti l'indirizzo IP principale del tuo server nel campo `'Hostname (or IP address)'` e fai clic su Open.
  Nota: la porta predefinita per SSH è la 22, ma puoi modificarla sul server dopo la tua prima connessione stabilita correttamente.
2. Il server RedHat ti richiede un nome utente e una password. Immetti le tue informazioni utente/password root per il server.
3. Salva i dettagli della connessione (indirizzo IP e porta) nelle sessioni immettendo l'indirizzo IP e la porta. Crea un titolo per queste proprietà della connessione come ad esempio "My Server" e fai clic su Save.
  Quando ti colleghi al tuo server, dovrai solo evidenziare la sessione salvata e fare clic su Open.

Puoi collegarti al tuo server utilizzando la rete pubblica.
Puoi anche collegarti utilizzando la rete privata. Segui le istruzioni in {{site.data.keyword.slportal_full}} per la connessione alla VPN e quindi utilizza SSH per collegarti al tuo indirizzo IP privato.
