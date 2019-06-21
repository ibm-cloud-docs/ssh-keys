---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Schlüssel entfernen
{: #removing-an-ssh-key}

Wenn ein in der {{site.data.keyword.cloud}}-Konsole gespeicherter SSH-Schlüssel veraltet ist oder nicht mehr benötigt wird, können Sie den Schlüssel entfernen. Entfernen Sie veraltete SSH-Schlüssel so bald wie möglich, um sicherzustellen, dass genügend Platz für weitere, gültige Schlüssel vorhanden ist.
{:shortdesc}

## Vorbereitung
Navigieren Sie zuerst zum Gerätemenü und stellen Sie sicher, dass Sie über die korrekten Kontoberechtigungen zum Ausführen dieser Aufgabe verfügen. 

* Navigieren Sie zum Gerätemenü der Konsole. Weitere Informationen finden Sie in [Zu Geräten navigieren](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Stellen Sie sicher, dass Sie über die erforderlichen Kontoberechtigungen und Gerätezugriff verfügen. Nur der Kontoeigner oder ein Benutzer mit der Berechtigung **Benutzer verwalten** der klassischen Infrastruktur kann die Berechtigungen anpassen. 

Weitere Informationen zu Berechtigungen finden Sie in [Berechtigungen der klassischen Infrastruktur](/docs/iam?topic=iam-infrapermission#infrapermission) und in [Gerätezugriff verwalten](/docs/vsi?topic=virtual-servers-managing-device-access).

## SSH-Schlüssel entfernen

1. Wählen Sie im Menü **Geräte** die Option **Verwalten > SSH-Schlüssel** aus. 
2. Klicken Sie neben dem SSH-Schlüssel, den Sie entfernen möchten, auf das Symbol **Entfernen**.
3. Klicken Sie zur Bestätigung auf **Ja**. 

## Nächste Schritte

Nach dem Entfernen eines SSH-Schlüssels wird dieser umgehend aus der Liste entfernt. Der Schlüssel kann nicht mehr verwendet werden, wenn Sie ein neues Gerät bereitstellen oder das Betriebssystem für ein vorhandenes Gerät erneut laden. Wenn der Schlüssel fälschlicherweise entfernt wird oder wieder zur {{site.data.keyword.cloud_notm}}-Konsole hinzugefügt werden soll, lesen Sie die Informationen in [SSH-Schlüssel hinzufügen](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key).
