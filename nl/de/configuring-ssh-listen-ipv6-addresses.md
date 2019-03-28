---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IPv6 addresses, Linux server, IPv6

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH für die Empfangsbereitschaft für IPv6-Adresse konfigurieren
{: #configuring-ssh-to-listen-on-ipv6-addresses}

Wenden Sie das folgende Verfahren an, um SSH für die IPv6-Empfangsbereitschaft auf einem Linux-Server zu aktivieren:
1. Suchen Sie nach der Datei: /etc/ssh/sshd_config.
2. Suchen Sie nach der Zeile, die `ListenAddress` enthält.
3. Entfernen Sie die Kommentarzeichen aus der Zeile `#ListenAddress ::`:
```
ListenAddress ::
```

Damit wird `sshd` an jede Adresse auf Ihrem Gerät gebunden.
