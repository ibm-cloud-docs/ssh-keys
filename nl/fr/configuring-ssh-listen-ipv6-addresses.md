---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuration de SSH pour écouter sur des adresses IPv6

Suivez la procédure suivante afin d'activer SSH sur un serveur Linux pour écouter sur des adresses IPv6 :
1. Localisez le fichier : /etc/ssh/sshd_config.
2. Localisez la ligne contenant `ListenAddress`.
3. Supprimez la mise en commentaire de la ligne `#ListenAddress ::`, comme suit :
```
ListenAddress ::
```

Cette action associe `sshd` à toutes les adresses sur votre appareil.
