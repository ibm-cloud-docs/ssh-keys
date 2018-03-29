---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH für die Empfangsbereitschaft nur für ein privates Netz konfigurieren

Sie können Ihren Server zusätzlich sichern, indem Sie SSHD nur im Back-End-Netz ausführen. Deshalb müssen Sie sich jedes Mal neu mit VPN verbinden, wenn Sie auf SSH zugreifen müssen.

1. Suchen Sie die folgende Datei. Verwenden Sie diese Datei, um die IP-Adresse für `sshd` zu definieren.
```
# nano /etc/ssh/sshd_config
```

2. Suchen Sie die Zeile, die `ListenAddress 0.0.0.0` enthält. Wenn sie mit dem Zeichen '#' beginnt, entfernen Sie dieses Zeichen. Legen Sie die IP-Adresse auf die IP fest, für die eine Empfangsbereitschaft bestehen soll. Sie können Ihre interne IP-Adresse finden, indem Sie im {{site.data.keyword.slportal_full}} *Hardware* auswählen.
3. Nachdem Sie die Änderung vorgenommen haben, starten Sie den SSH-Service erneut:
```
# service sshd restart
```

Die Verbindung für Ihr aktuelles Shellfenster wird beim Neustart des Service nicht unterbrochen. Überprüfen Sie, ob Sie über den neuen SSH-Port eine Verbindung zum Server herstellen können, bevor Sie Ihr aktuelles Shellfenster verlassen. Wenn ein Problem besteht, kann SSHD nicht erneut gestartet werden und Sie müssen über eine alternative Methode eine Verbindung zum Server herstellen.
