---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuration de SSH pour écouter uniquement sur un réseau privé
{: #configuring-ssh-to-listen-only-on-a-private-network}

Vous pouvez renforcer la sécurité de votre serveur en exécutant SSHd uniquement sur un réseau de back end. Par conséquent, vous devez vous connecter au réseau privé virtuel (VPN) chaque fois que vous avez besoin d'accéder à SSH.

1. Localisez le fichier suivant. Utilisez ce fichier pour définir l'adresse IP de `sshd`.
```
# nano /etc/ssh/sshd_config
```

2. Localisez la ligne contenant `ListenAddress 0.0.0.0`. Si elle commence par le caractère '#', supprimez ce caractère. Définissez l'adresse IP avec l'adresse IP que vous voulez utiliser pour écouter. Vous pouvez obtenir votre adresse IP interne en sélectionnant *Matériel* dans le portail {{site.data.keyword.slportal_full}}.
3. Une fois la modification effectuée, redémarrez le service SSH :
```
# service sshd restart
```

Votre fenêtre d'interpréteur de commandes actuelle ne se déconnectera pas lors du redémarrage du service. Vérifiez que vous pouvez vous connecter au serveur via le nouveau port SSH avant de quitter cette fenêtre. En cas de problème, SSHd ne parvient pas à redémarrer et vous devez recourir à une autre méthode pour vous connecter au serveur.
