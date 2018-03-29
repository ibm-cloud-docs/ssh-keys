---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH für die Ausführung auf einem Nicht-Standardport konfigurieren

Befolgen Sie diese Schritte, um die Ausführung von SSH auf einem Nicht-Standardport zu erzwingen:

1. Öffnen Sie /etc/ssh/sshd_config in einem Texteditor. Das folgende Beispiel gilt für Editor vi.
```
# vi /etc/ssh/sshd_config
```
 
2. Blättern Sie zur folgenden Zeile:
```
# Port 22
```
 
3. Entfernen Sie die Kommentarzeichen und bearbeiten Sie diese Zeile, sodass sie den neuen Port abbildet.
```
Port 2255
``` 
(Dies kann auf einen beliebigen Nicht-Standardport festgelegt sein)
 
4. Speichern und verlassen Sie die Datei und starten Sie SSH erneut.
```
# /etc/init.d/sshd restart
```

5. Wenn Sie mittels SSH über Port 22 mit dem Server verbunden sind, wird Ihre Verbindung abgebrochen und Sie müssen über den neuen Port eine neue Verbindung herstellen.
