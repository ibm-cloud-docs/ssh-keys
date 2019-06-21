---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH access, public network SSH accessibility, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Limitazione dell'accesso SSH su una rete pubblica
{: #restricting-ssh-access-on-a-public-network}

L'accessibilità SSH fornisce agli utenti la capacità di accedere in modo sicuro a un dispositivo tramite una connessione internet. SSH è disponibile sui dispositivi {{site.data.keyword.cloud}} sia sulla rete pubblica che privata. Tuttavia, puoi limitare l'accessibilità SSH sulla rete pubblica a meno che non sia necessaria per scopi di business eccezionali. Limitando l'accesso SSH sulla rete pubblica, gli utenti possono ancora accedere al dispositivo sulla rete privata, ma il rischio di accesso di utenti sconosciuti sulla rete pubblica è ridotto. Se l'accessibilità SSH sulla rete pubblica è necessaria, puoi trasferire SSH su un numero di porta personalizzato per un livello di sicurezza aggiuntivo.
{:shortdesc}

Segui questa procedura per limitare l'accesso SSH sulla rete pubblica.
1. Accedi a **Private Network** con [VPN ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://www.softlayer.com/vpn-access){: new_window}.
2. Accedi a **Private IP Address** del Bare Metal Server tramite SSH.
3. Immetti il seguente comando per aprire il file `sshd_config` per la modifica:
  > `vi /etc/ssh/sshd_config`
4. Rimuovi **hash (#)** da una riga `ListenAddress` per annullare il commento nella riga.
5. Immetti **Private IP Address** per il Bare Metal Server nella riga `ListenAddress` in cui è stato annullato il commento.
6. Esegui il comando `:wq` per salvare le modifiche e uscire dal file.
7. Riavvia il servizio sshd
  > `service sshd restart`
8. Verifica gli aggiornamenti all'accessibilità SSH tentando l'accesso SSH sull'indirizzo IP pubblico del Bare Metal Server.<br><br><table border="1"><tr><th>Se una connessione...</th><th>Poi...</th></tr><tr><td>Non può essere effettuata</td><td>Le modifiche apportate all'accessibilità SSH hanno avuto esito positivo. Nessuna ulteriore azione è richiesta.</td></tr><tr><td>Può essere effettuata</td><td>Le modifiche apportate all'accessibilità SSH hanno avuto esito negativo. Ripeti i passi precedenti per ritentare la limitazione SSH. Se gli errori persistono, contatta il supporto.</td></tr></table>

## Passi successivi

Dopo aver correttamente limitato l'accesso SSH, gli utenti non potranno accedere al dispositivo tramite SSH quando non si connettono attraverso la rete privata. Questa azione può essere annullata in qualsiasi momento aggiungendo l'hash (#) alla riga di cui è stato annullato il commento, che restituisce la riga ai commenti.
