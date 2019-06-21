---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Schlüssel hinzufügen
{: #adding-an-ssh-key}

Sofern Sie über die entsprechenden Benutzerberechtigungen verfügen, können Sie Ihrem Konto SSH-Schlüssel hinzufügen. Jedes Konto kann bis zu 100 SSH-Schlüssel gleichzeitig besitzen. SSH-Schlüssel werden meistens für den [Prozess zum erneuten Laden des Betriebssystems](/docs/software?topic=software-reloading-the-os#reloading-the-os) verwendet. Sie können aber zusätzlich auch bei der Bereitstellung eines neuen Geräts verwendet werden.
{:shortdesc}

## Vorbereitung
Generieren Sie als ersten Schritt den öffentlichen SSH-Schlüssel. Navigieren Sie zum Gerätemenü und stellen Sie sicher, dass Sie über die korrekten Kontoberechtigungen zum Ausführen dieser Aufgabe verfügen. 

* [Generieren Sie den öffentlichen SSH-Schlüssel ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://help.github.com/articles/generating-ssh-keys){: new_window} für das Gerät. 
* Navigieren Sie zum Gerätemenü der Konsole. Weitere Informationen finden Sie in [Zu Geräten navigieren](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Stellen Sie sicher, dass Sie über die erforderlichen Kontoberechtigungen und Gerätezugriff verfügen. Nur der Kontoeigner oder ein Benutzer mit der Berechtigung **Benutzer verwalten** der klassischen Infrastruktur kann die Berechtigungen anpassen. 

Weitere Informationen zu Berechtigungen finden Sie in [Berechtigungen der klassischen Infrastruktur](/docs/iam?topic=iam-infrapermission#infrapermission) und in [Gerätezugriff verwalten](/docs/vsi?topic=virtual-servers-managing-device-access).

## SSH-Schlüssel zum Konto hinzufügen
Führen Sie die folgenden Schritte aus, um einen SSH-Schlüssel zu Ihrem Konto hinzuzufügen. 

1. Wählen Sie im Menü **Geräte** die Option **Verwalten > SSH-Schlüssel** aus. 
2. Klicken Sie auf **Hinzufügen**.
3. Klicken Sie auf **Durchsuchen**, um die Datei mit dem öffentlichen Schlüssel zu finden, oder geben Sie sie manuell in das Textfeld **Schlüsselinhalte** ein.
4. Geben Sie im Feld **Bezeichnung** einen **Kurznamen** für den SSH-Schlüssel ein.
5. Geben Sie bei Bedarf im Feld **Anmerkungen** zutreffende Anmerkungen ein.
6. Klicken Sie auf **Hinzufügen**, um den SSH-Schlüssel hinzuzufügen. 

## Nächste Schritte

Nach dem Hinzufügen eines SSH-Schlüssels wird dieser in der Liste der SSH-Schlüssel angezeigt. Sie können jederzeit die [Schlüssel-Details bearbeiten](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key). Sie können auch den [SSH-Schlüssel entfernen](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key), sodass er nicht mehr in der Liste erscheint. Entfernen Sie veraltete SSH-Schlüssel so bald wie möglich, um sicherzustellen, dass genügend Platz verfügbar ist, wenn Sie weitere Schlüssel hinzufügen müssen.
