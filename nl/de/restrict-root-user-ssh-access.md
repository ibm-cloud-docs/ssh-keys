---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Zugriff für Rootbenutzer unzugänglich machen
{: #restricting-the-root-user-from-ssh-access}

Jedes Linux-System im {{site.data.keyword.cloud}}-Netz hat einen Rootbenutzer mit Administratorberechtigungen. Innerhalb von Linux können Sie Wheel-Gruppen erstellen, die den Benutzern durch "sudo" ähnliche Berechtigungen geben wie dem Rootbenutzer, ohne dass Rootbenutzer-Berechtigungsnachweise erforderlich wären. Nach dem Erstellen einer Wheel-Gruppe mit sudo-Stammberechtigungen können Sie den SSH-Zugriff für Benutzer in dieser Gruppe unzugänglich machen. Durch diese Einschränkung der Benutzer schützen Sie das Gerät vor Sicherheitslücken, die sich auf die Netzzugänglichkeit auswirken könnten. Benutzer, die Teil der Wheel-Gruppe sind, können weiterhin jederzeit Verwaltungsfunktionen am Gerät ausführen.
{:shortdesc}

Befolgen Sie diese Schritte, um den SSH-Zugriff für Rootbenutzer unzugänglich zu machen.

1. Öffnen Sie die Datei 'etc/group' und prüfen Sie, ob sie eine Zeile enthält, in der eine Wheel-Gruppe definiert wird:
```
wheel:x:10:root
```

    Findet sich in der Datei keine solche Zeile, erstellen Sie sie.

2. Fügen Sie zur Zeile für die Wheel-Gruppe mindestens einen Benutzer hinzu:
```
wheel:x:10:root, user1
```

    Benutzer, die zur Wheel-Gruppe hinzugefügt werden, haben dieselben Berechtigungen wie der Rootbenutzer, verwenden aber für ihren Zugriff auf das System ihren eindeutigen Benutzernamen.
3. Führen Sie den Befehl `:wq` aus, um Änderungen zu speichern und die Datei zu verlassen.
4. Öffnen Sie `/etc/ssh/sshd_config`.
5. Ändern Sie die Zeile `PermitRootLogin yes` in `PermitRootLogin no`.
6. Führen Sie den Befehl `:wq` aus, um Änderungen zu speichern und die Datei zu verlassen.
7. Geben Sie in der **Befehlszeile** `visudo` ein, um Befehlsberechtigungen zu generieren.
8. Entfernen Sie das **Hash (#)** aus der folgenden Zeile, um die Kommentarzeichen aus der Zeile zu entfernen:
```
# %wheel ALL=(ALL) ALL
```

   Durch das Entfernen der Kommentarzeichen aus dieser Zeile können Benutzer in der Wheel-Gruppe alle Befehle ausführen.
   {:note}

9. Führen Sie den Befehl `:wq` aus, um Änderungen zu speichern und die Datei zu verlassen.
10. Führen Sie in der Befehlszeile den folgenden Befehl aus:
```
vi /etc/pam.d/su
```

11. Entfernen Sie das **Hash (#)** aus der folgenden Zeile, um die Kommentarzeichen aus der Zeile zu entfernen:
```
#auth required pam_wheel.so use_uid
```

   Nach dem Entfernen der Kommentarzeichen aus dieser Zeile müssen Benutzer Teil der Wheel-Gruppe sein, damit sie die Berechtigung haben, alle Befehle auszuführen.
   {:note}
   
12. Führen Sie den Befehl `:wq` aus, um Änderungen zu speichern und die Datei zu verlassen.
13. Führen Sie den folgenden Befehl aus, um alle Änderungen zu speichern und SSH erneut zu starten:
```
# etc/init.d/ssh restart
```

## Nächste Schritte

Nachdem Sie den SSH-Zugriff für den Rootbenutzer unzugänglich gemacht haben, kann sich der Rootbenutzer nicht mehr bei SSH anmelden. Wenn ein Benutzer bisher unter dem Rootbenutzer SSH-Zugriff zum Server hatte, schlägt die Verbindung fehl, nach dem SSH in der vorangehenden Prozedur erneut gestartet wurde. Alle künftigen Versuche, durch den Rootbenutzer eine Verbindung zu SSH herzustellen, schlagen fehl. Um diese Änderungen rückgängig zu machen, wiederholen Sie die Schritte und ändern Sie "no" für `PermitRootLogin` zurück in "yes" für `PermitRootLogin`.
