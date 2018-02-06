---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH-Schlüssel hinzufügen

Sofern Sie über die entsprechenden Benutzerberechtigungen verfügen, können Sie Ihrem Konto SSH-Schlüssel hinzufügen. Jedes Konto kann bis zu 100 SSH-Schlüssel gleichzeitig besitzen. Im {{site.data.keyword.slportal_full}} werden SSH-Schlüssel meistens für den [Prozess zum erneuten Laden des Betriebssystems](../software/vsi_reload_os.html){:new_window} verwendet. Sie können aber zusätzlich auch bei der Bereitstellung eines neuen Geräts verwendet werden. 

**Anmerkung:** [Generieren Sie den öffentlichen SSH-Schlüssel ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://help.github.com/articles/generating-ssh-keys){: new_window} mit dem Gerät, für das Sie gerade einen Schlüssel hinzufügen, bevor Sie einen SSH-Schlüssel zu Ihrem Konto hinzufügen. 

Zum Hinzufügen eines SSH-Schlüssels zu Ihrem Konto befolgen Sie diese Schritte.
1. Greifen Sie auf den Bildschirm **SSH-Schlüssel** zu. Informationen hierzu finden Sie unter [Einführung in SSH-Schlüssel](index.html).
2. Klicken Sie oben auf dem Bildschirm auf die Registerkarte **Hinzufügen**.
3. Klicken Sie auf **Durchsuchen**, um die Datei mit dem öffentlichen Schlüssel zu finden, oder geben Sie sie manuell in das Textfeld **Schlüsselinhalte** ein.
4. Geben Sie im Feld **Bezeichnung** einen **Kurznamen** für den SSH-Schlüssel ein.
5. Geben Sie bei Bedarf im Feld **Anmerkungen** zutreffende Anmerkungen ein.
6. Klicken Sie auf **Hinzufügen**, um den SSH-Schlüssel hinzuzufügen. Um die Aktion abzubrechen, klicken Sie auf **Abbrechen**.

## Nächste Schritte

Nach dem Hinzufügen eines SSH-Schlüssels wird dieser in der Liste der SSH-Schlüssel angezeigt.
Sie können jederzeit die [Schlüssel-Details bearbeiten](edit-details-ssh-key.html). Sie können auch den [SSH-Schlüssel entfernen](remove-ssh-key.html){:new_window}, sodass er nicht mehr in der Liste erscheint. Entfernen Sie veraltete SSH-Schlüssel so bald wie möglich, um sicherzustellen, dass genügend Platz verfügbar ist, wenn Sie weitere Schlüssel hinzufügen müssen.
