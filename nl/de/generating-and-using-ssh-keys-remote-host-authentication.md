---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Schlüssel zur Authentifizierung eines fernen Hosts erstellen und verwenden

Mit SSH-Schlüsseln können Sie sich bei einem SSH-Server identifizieren, der eine Verschlüsselung mit öffentlichem Schlüssel und Challenge/Response-Verfahren verwendet. Ein unmittelbarer Vorteil dieser Methode gegenüber der Kennwortauthentifizierung liegt darin, dass Sie vom Server authentifiziert werden können, ohne Ihr Kennwort über das Netz senden zu müssen. Sie können diese Methode auch zusammen mit einer Automatisierung verwenden, da sie die unbeaufsichtigte Serverkommunikation zulässt.

## SSH-Schlüssel unter Linux generieren

Zum Generieren eines SSH-Schlüssels auf Ihrem Linux-Server führen Sie den Befehl `ssh-keygen` aus. Wenn Sie den Typ des generierten Schlüssels und die zum Generieren des Schlüssels verwendeten Signaturalgorithmen anpassen möchten, können Sie Flags in den Befehl aufnehmen. In diesem Beispiel wird ein Standard-2048-Bit-RSA-Schlüssel ohne Kennphrase generiert. Der Befehl fordert Sie zur Eingabe eines Speicherorts für den Schlüssel (Standardwert ist $HOME/.ssh/) sowie einer Kennphrase zum Sichern des SSH-Schlüssels auf.

    root@bck2:/etc# ssh-keygen
    Öffentlich/privates RSA-Schlüsselpaar wird generiert.
    Datei zum Speichern des Schlüssels eingeben (/root/.ssh/id_rsa):
    Kennphrase eingeben (leer für 'keine Kennphrase'):
    Dieselbe Kennphrase erneut eingeben:
    Ihre Identifikation wurde unter /root/.ssh/id_rsa gespeichert.
    Ihr öffentlicher Schlüssel wurde unter /root/.ssh/id_rsa.pub gespeichert.
    Der Schlüssel-Fingerabdruck ist:
    SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx root@bck2.example.com
    Das randomart-Bild des Schlüssels ist:
    +---[RSA 2048]----+
    |.  oo*%=+o..     |
    |.++.oX+=. .      |
    |..+ooo=. .       |
    |   E.+. .o.      |
    |    +   S..+     |
    |     . +. =      |
    |      o  = o     |
    |      .o+ +      |
    |       +o.       |
    +----[SHA256]-----+

## Öffentlichen Schlüssel auf ferne Hosts kopieren

Zur Authentifizierung bei einem fernen Host unter Verwendung Ihres öffentlichen SSH-Schlüssels verwenden Sie den Befehl `ssh-copy-id`. Verwenden Sie das Flag `-i`, um den öffentlichen Schlüssel anzugeben, der auf den fernen Host kopiert werden soll.

    root@bck2: # ssh-copy-id -i /root/.ssh/id_rsa.pub root@10.176.18.15
    /usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/root/.ssh/id_rsa.pub"
    Die Authentizität des Hosts '10.176.18.15 (10.176.18.15)' kann nicht festgestellt werden.
    Der ECDSA-Schlüssel-Fingerabdruck ist SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.

    Möchten Sie weiterhin versuchen, die Verbindung herzustellen (ja/nein)? ja
    /usr/bin/ssh-copy-id: INFO: Es wird versucht, sich mit dem/den neuen Schlüssel(n) anzumelden, um alle bereits installierten herauszufiltern
    /usr/bin/ssh-copy-id: INFO: Noch 1 Schlüssel muss installiert werden -- wenn Sie jetzt eine Eingabeaufforderung erhalten, geht es um die Installation der neuen Schlüssel
    Kennwort von root@10.176.18.15:

    Anzahl der hinzugefügten Schlüssel: 1

    Versuchen Sie sich jetzt bei der Maschine anzumelden mit:   "ssh 'root@10.176.18.15'"
    und stellen Sie sicher, dass nur der/die gewünschte(n) Schlüssel hinzugefügt wurde(n).

***Anmerkung:*** Der Befehl 'ssh-copy-id' hängt die Schlüssel an die Datei '.ssh/authorized_key' des fernen Hosts an.

## Testen, ob der Schlüssel richtig kopiert wurde

Um zu testen, ob der öffentliche Schlüssel richtig auf den fernen Host kopiert wurde, stellen Sie einfach eine SSH-Verbindung zum fernen Host her.

    root@bck2:/etc# ssh root@10.176.18.15
    Willkommen bei Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * Dokumentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/advantage

      Rufen Sie den Cloud-Support ab mit Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 Pakete können aktualisiert werden.
    0 Aktualisierungen sind Sicherheitsupdates.

    Letzte Anmeldung: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

Wie Sie sehen, gibt es keine Aufforderung zur Eingabe des Kennworts, wenn eine SSH-Verbindung zum fernen Host hergestellt wird.

## SSH-Schlüssel mit Kennphrase

Durch die Angabe einer Kennphrase für Ihren SSH-Schlüssel wird eine zusätzliche Sicherheitsebene hinzugefügt. Dies kann allerdings auch zu Problemen führen, wenn Sie versuchen, automatisierte Scripts auszuführen, die die Verwendung des geschützten Schlüssels erfordern. 

Der SSH-Agent kann Ihre Schlüssel für Sie verwalten. Sie müssen die Kennphrase nur einmal eingeben. Der SSH-Agent speichert Ihren Schlüssel ab und extrahiert ihn, wenn er gebraucht wird. Damit der SSH-Agent Ihre Schlüssel verwaltet, geben Sie folgenden Befehl ein:

    eval $(ssh-agent)

Nachdem das Programm begonnen hat, den Befehl 'ssh-add' zu verwenden, um Ihren öffentlichen Schlüssel zum Agenten hinzuzufügen, sucht das Dienstprogramm 'ssh-add' nach Standard-Schlüsselnamen (einer von ihnen ist 'id_rsa') und fügt sie dem SSH-Agenten hinzu. Nach der Eingabe Ihres Kennworts wird der "freigegebene" Schlüssel zusammen mit dem SSH-Agenten gespeichert und kann zur Authentifizierung bei anderen Servern verwendet werden.

    root@bck1:~# ssh-add
    Kennphrase für /root/.ssh/id_rsa eingeben:
    Identität hinzugefügt: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

Jedes Mal, wenn Sie eine neue Terminalsitzung öffnen, werden Sie zur Eingabe der Kennphrase für den Schlüssel aufgefordert. Es besteht die Möglichkeit, die folgenden Befehle auszuführen, um Ihre Datei `.bash_profile` anzuhängen, sodass der SSH-Agent mit jeder Bash-Sitzung gestartet und Ihr Schlüssel hinzugefügt wird.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
