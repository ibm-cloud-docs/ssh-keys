---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH für die Empfangsbereitschaft für IPv6-Adresse konfigurieren

Wenden Sie das folgende Verfahren an, um IPv6 für Linux-Server-SSH zu aktivieren:
1. Suchen Sie nach der Datei: /etc/ssh/sshd_config.
2. Suchen Sie nach der Zeile, die `ListenAddress` enthält.
3. Entfernen Sie die Kommentarzeichen aus der Zeile `#ListenAddress ::`:
```
ListenAddress ::
```

Damit wird `sshd` an jede Adresse auf Ihrem Gerät gebunden.
