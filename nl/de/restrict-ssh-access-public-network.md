---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Zugriff in einem öffentlichen Netz beschränken

Der SSH-Zugriff ermöglicht Benutzern den sicheren Zugriff auf ein Gerät über eine Internetverbindung. SSH steht für {{site.data.keyword.cloud}}-Geräte sowohl im öffentlichen als auch im privaten Netz zur Verfügung. Allerdings sollten Sie den SSH-Zugriff über das öffentliche Netz einschränken, wenn er nicht für eine besondere Geschäftsanforderung benötigt wird. Bei Einschränkung des SSH-Zugriffs über das öffentliche Netz können Benutzer weiterhin über das private Netz auf ein Gerät zugreifen, aber das Risiko, dass unbekannte Benutzer aus dem öffentlichen Netz auf das Gerät zugreifen, ist gemindert. Wenn der SSH-Zugriff über das öffentliche Netz notwendig ist, können Sie SSH auf eine angepasste Portnummer übertragen, um eine weitere Sicherheitsebene zu erhalten.
{:shortdesc}

Befolgen Sie diese Schritte, um den SSH-Zugriff über das öffentliche Netz zu beschränken.
1. Greifen Sie über [VPN ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://www.softlayer.com/vpn-access){: new_window} auf das **private Netz** zu.
2. Melden Sie sich mittels SSH bei der **privaten IP-Adresse** des Bare-Metal-Servers an.
3. Führen Sie den folgenden Befehl aus, um die Datei `sshd_config` für Bearbeitungen zu öffnen:
  > `vi /etc/ssh/sshd_config`
4. Entfernen Sie das **Hash (#)** aus einer `ListenAddress`-Zeile, um die Kommentarzeichen aus der Zeile zu entfernen.
5. Geben Sie die **private IP-Adresse** für den Bare-Metal-Server in der `ListenAddress`-Zeile ein, aus der die Kommentarzeichen entfernt wurden.
6. Führen Sie den Befehl `:wq` aus, um die Änderungen zu speichern und die Datei zu verlassen.
7. Starten Sie den SSHD-Service erneut.
  > `service sshd restart`
8. Testen Sie die Aktualisierungen am SSH-Zugriff, indem Sie versuchen, über die öffentliche IP-Adresse des Bare-Metal-Servers auf SSH zuzugreifen.<br><br><table border="1"><tr><th>Wenn eine Verbindung...</th><th>Dann ist...</th></tr><tr><td>... nicht möglich.</td><td>Die am SSH-Zugriff vorgenommenen Änderungen waren erfolgreich. Es ist keine weitere Aktion erforderlich.</td></tr><tr><td>... möglich.</td><td>Die am SSH-Zugriff vorgenommenen Änderungen waren nicht erfolgreich. Wiederholen Sie die obigen Schritte, um die Beschränkung des SSH-Zugriffs erneut zu versuchen. Wenn die Probleme bestehen bleiben, wenden Sie sich bitte an den Support.</td></tr></table>

## Nächste Schritte

Nachdem Sie den SSH-Zugriff erfolgreich eingeschränkt haben, können Benutzer nicht mehr mittels SSH auf das Gerät zugreifen, sofern sie nicht über das private Netz eine Verbindung herstellen. Diese Aktion kann jederzeit rückgängig gemacht werden, indem das Hash (#) der Zeile, aus der die Kommentarzeichen entfernt wurden, wieder hinzugefügt wird, sodass die Zeile wieder zum Kommentar wird.
