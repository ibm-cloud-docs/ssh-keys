---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuration de SSH pour écouter uniquement sur un réseau privé

Vous pouvez renforcer la sécurité de votre serveur en exécutant SSHd uniquement sur un réseau de back end. Par conséquent, il vous faudra vous connecter au réseau privé virtuel (VPN) chaque fois que vous aurez besoin d'accéder à SSH.

1. Localisez le fichier suivant. Utilisez ce fichier pour définir l'adresse IP de `sshd`.
```
# nano /etc/ssh/sshd_config
```

2. Localisez la ligne contenant `ListenAddress 0.0.0.0`. Si elle commence par le caractère '#', supprimez ce caractère. Définissez l'adresse IP avec l'adresse IP que vous voulez utiliser pour écouter. Vous pouvez obtenir votre adresse IP interne en sélectionnant *Matériel* dans le portail {{site.data.keyword.slportal_full}}.
3. Une fois la modification effectuée, redémarrez le service SSH :
```
# service sshd restart
```

Votre fenêtre d'interpréteur de commandes actuelle ne se déconnectera pas lors du redémarrage du service. Vérifiez que vous pouvez vous connecter au serveur via le nouveau port SSH avant de quitter cette fenêtre. En cas de problème, SSHd ne parviendra pas à redémarrer et il vous faudra recourir à une autre méthode pour vous connecter au serveur.
