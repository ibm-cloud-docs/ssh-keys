---
copyright:
  years: 2014, 2018
lastupdated: "2018-08-15"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Informationen zu SSH-Schlüsseln

SSH-Schlüssel werden von SSH-Servern verwendet, um einen Benutzer oder ein Gerät durch eine Verschlüsselung mit öffentlichem Schlüssel zu identifizieren. SSH-Schlüssel setzen sich aus einer alphanumerischen Kombination zusammen und sind für das Gerät, dem sie zugewiesen sind, eindeutig. Benutzer mit der entsprechenden Berechtigung können SSH-Schlüssel zu jeder Zeit hinzufügen, bearbeiten oder löschen, indem sie das {{site.data.keyword.slportal_full}} verwenden.

SSH-Schlüssel können während der Bereitstellung oder über ein [erneutes Laden des Betriebssystems](../software/vsi_reload_os.html) angefordert werden.


SSH-Schlüssel ermöglichen den Zugriff auf ein Gerät, ohne dass für jeden öffentlichen Schlüssel, der im Gerät implementiert ist, ein Kennwort von den entsprechenden Clients verwendet werden muss. Durch Hinzufügen eines SSH-Schlüssels zu einem Gerät greift das Gerät, dem der SSH-Schlüssel bereitgestellt wurde, ohne Kennwort auf das Gerät für den entsprechenden Schlüssel zu.
