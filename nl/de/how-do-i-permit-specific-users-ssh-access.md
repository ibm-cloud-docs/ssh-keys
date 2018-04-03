---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Zugriff für einen Benutzer erteilen 

Befolgen Sie diese Schritte, um einem oder mehreren Benutzern SSH-Zugriff zu erteilen. Diese Schritte zeigen, wie diese Datei konfiguriert werden kann:

1. Suchen Sie die folgende OpenSSH-Datei:
```
/etc/ssh/sshd_config
```
  
2. Erstellen Sie ein Backup dieser Datei, um sie bei Bedarf zurücksetzen zu können. Beispiel:
```
cp /etc/ssh/sshd_config{,.'date +%s'}
```
  
3. Bearbeiten Sie die Datei, indem Sie die OpenSSH-Schlüsselwörter verwenden.


## OpenSSH-Schlüsselwörter

### AllowGroups 

Nach diesem Schlüsselwort beziehen Sie eine Liste der Gruppennamenmuster ein. Trennen Sie die Muster durch Leerzeichen. Wenn Sie **Anmeldung** angeben, ist es nur für Benutzer zugänglich, deren primäre oder ergänzende Gruppenliste mit einem der Muster übereinstimmt. Sie können `"*" und "?"` als Platzhalter in den Mustern verwenden. Nur Gruppennamen sind gültig; eine numerische Gruppen-ID wird nicht erkannt. Standardmäßig ist **Anmeldung** für alle Gruppen zulässig.

### AllowUsers 

Nach diesem Schlüsselwort beziehen Sie eine Liste der Benutzernamenmuster ein. Trennen Sie die Muster durch Leerzeichen. Wenn Sie **Anmeldung** angeben, ist es nur für Benutzernamen zugänglich, die mit einem der Muster übereinstimmen. Sie können `"*" und "?"` als Platzhalter in den Mustern verwenden. Nur Benutzernamen sind gültig; eine numerische Benutzer-ID wird nicht erkannt. Standardmäßig ist **Anmeldung** für alle Benutzer zulässig. Wenn das Muster das Format USER@HOST hat, werden USER und HOST getrennt überprüft, wodurch Anmeldungen auf bestimmte Benutzer von bestimmten Hosts beschränkt werden.

### DenyGroups 

Nach diesem Schlüsselwort beziehen Sie eine Liste der Gruppennamenmuster ein. Trennen Sie die Muster durch Leerzeichen. Wenn Sie **Anmeldung** angeben, ist es für Benutzer, deren primäre oder ergänzende Gruppenliste mit einem der Muster übereinstimmt, unzulässig. Sie können `"*" und "?"` als Platzhalter in den Mustern verwenden. Nur Gruppennamen sind gültig; eine numerische Gruppen-ID wird nicht erkannt. Standardmäßig ist **Anmeldung** für alle Gruppen zulässig.

### DenyUsers 

Nach diesem Schlüsselwort beziehen Sie eine Liste der Benutzernamenmuster ein. Trennen Sie die Muster durch Leerzeichen. Wenn Sie **Anmeldung** angeben, ist es für Benutzernamen, die mit einem der Muster übereinstimmen, unzulässig. Sie können `"*" und "?"` als Platzhalter in den Mustern verwenden. Nur Benutzernamen sind gültig; eine numerische Benutzer-ID wird nicht erkannt. Standardmäßig ist **Anmeldung** für alle Benutzer zulässig.  Wenn das Muster das Format USER@HOST hat, werden USER und HOST getrennt überprüft, wodurch Anmeldungen auf bestimmte Benutzer von bestimmten Hosts beschränkt werden.

## Beispiel

Im folgenden Beispiel dürfen sich nur zwei bestimmte Benutzer, `admin` und `user1`, beim Server anmelden.
**Anmerkung:** Sie können zum Zurückweisen von eine ähnliche Methode verwenden, bei der Sie die Schlüsselwörter `DenyGroups` und `DenyUsers` verwenden.
```
AllowUsers admin user1
```

Zur Vorbereitung einer späteren Erweiterung der Benutzer können Sie auf dem Server eine Gruppe erstellen, deren Mitglieder sich beim Server anmelden können. Sie können nach Bedarf einzelne Benutzer hinzufügen (ersetzen Sie dazu *`username`* durch den tatsächlichen Benutzer):

1. Fügen Sie in Shell eine Benutzergruppe hinzu, z. B. 'sshusers':
```
groupadd –r sshusers
```

2. Fügen Sie in Shell Benutzer zur Gruppe hinzu:
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. Erteilen Sie in der Datei 'sshd_config' der Gruppe 'sshusers' Zugriff:
```
AllowGroups sshusers
```

4. Überprüfen Sie, ob SSHD die neue Konfiguration ohne Unterbrechung liest:
```
/usr/sbin/sshd –t
```

```
echo $?
```

  Wenn Sie nach dem Befehl `echo $?` `0` erhalten, ist die neue Konfiguration richtig.

  Es kann auch sein, dass Sie Fehlernachrichten ähnlich den folgenden Beispielen erhalten:
```
sshd_config: line 112: Bad configuration option: allowuser
```

```
sshd_config: terminating, 1 bad configuration options
```

5. Nachdem Sie alle Fehler behoben und eine korrekte Konfiguration eingerichtet haben, starten Sie SSHD erneut. Dies ist ein Beispielbefehl in einem sysv-kompatiblen System:
  /etc/init.d/sshd restart

Stellen Sie sicher, dass Sie eine neue SSH-Sitzung erstellen, ohne Ihre bestehende Sitzung zu unterbrechen. Überprüfen Sie, ob Sie mit den Benutzern, die Sie hinzugefügt haben, alle Aktionen ausführen können.
