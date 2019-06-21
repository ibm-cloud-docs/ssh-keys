---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH key, key details, IBM Cloud infrastructure customer

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Details für einen SSH-Schlüssel bearbeiten
{: #editing-details-for-an-ssh-key}

Nach dem [Hinzufügen eines SSH-Schlüssels](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key) in der {{site.data.keyword.cloud}}-Konsole können Sie die Schlüssel-Details bearbeiten. Sie können die **Bezeichnung** (den Kurznamen, der zur leichteren Identifizierung des SSH-Schlüssels verwendet wird) und die **Anmerkungen** für den Schlüssel bearbeiten.
{:shortdesc}

## Vorbereitung
Navigieren Sie zuerst zum Gerätemenü und stellen Sie sicher, dass Sie über die korrekten Kontoberechtigungen zum Ausführen dieser Aufgabe verfügen. 

* Navigieren Sie zum Gerätemenü der Konsole. Weitere Informationen finden Sie in [Zu Geräten navigieren](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Stellen Sie sicher, dass Sie über die erforderlichen Kontoberechtigungen und Gerätezugriff verfügen. Nur der Kontoeigner oder ein Benutzer mit der Berechtigung **Benutzer verwalten** der klassischen Infrastruktur kann die Berechtigungen anpassen. 

Weitere Informationen zu Berechtigungen finden Sie in [Berechtigungen der klassischen Infrastruktur](/docs/iam?topic=iam-infrapermission#infrapermission) und in [Gerätezugriff verwalten](/docs/vsi?topic=virtual-servers-managing-device-access).

## Details des SSH-Schlüssels bearbeiten

Wenn Sie den Schlüssel selbst bearbeiten müssen, entfernen Sie ihn und fügen Sie den richtigen Schlüssel zur {{site.data.keyword.cloud_notm}}-Konsole hinzu. Der Fingerabdruck, der zusammen mit den Details für den SSH-Schlüssel aufgelistet ist, ist nicht der Schlüssel selbst, sondern eine Kurzsequenz von Byte, die beim Abruf des Schlüssels verwendet wird. Es kann sein, dass der Fingerabdruck den tatsächlichen SSH-Schlüssel in keiner Weise darstellt. 
{:note}

Führen Sie die folgenden Schritte au, um Details des SSH-Schlüssels zu bearbeiten.

1. Wählen Sie im Menü **Geräte** die Option **Verwalten > SSH-Schlüssel** aus.  
2. Klicken Sie an beliebiger Stelle im Feld **Bezeichnung** oder im Feld **Anmerkung**, um das Feld zur Bearbeitung zu öffnen.
3. Geben Sie den aktualisierten Text in das entsprechende Feld ein.
4. Klicken Sie an beliebiger Stelle in die Anzeige, um das Feld für weitere Bearbeitungen zu schließen.


## Nächste Schritte

Bearbeitete Details zu SSH-Schlüsseln werden in der Liste der SSH-Schlüssel sofort aktualisiert.
