---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuration de SSH pour écouter sur des adresses IPv6

Pour activer SSH sur un serveur Linux de manière à écouter sur des adresses IPv6, procédez comme suit :
1. Localisez le fichier : /etc/ssh/sshd_config.
2. Localisez la ligne contenant `ListenAddress`.
3. Supprimez la mise en commentaire de la ligne `#ListenAddress ::`, comme suit :
```
ListenAddress ::
```

Cette action associe `sshd` à toutes les adresses sur votre appareil.
