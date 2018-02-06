---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuration de SSH pour une exécution sur un port non standard

Suivez la procédure suivante pour forcer l'exécution de SSH sur un port non standard :

1. Ouvrez le fichier /etc/ssh/sshd_config dans un éditeur de texte. L'exemple suivant utilise l'éditeur vi.
```
# vi /etc/ssh/sshd_config
```
 
2. Accédez à la ligne suivante :
```
# Port 22
```
 
3. Supprimez la mise en commentaire et modifiez cette ligne pour prendre en compte le nouveau port.
```
Port 2255
``` 
(vous pouvez définir ici n'importe quel port non standard)
 
4. Sauvegardez et quittez le fichier, puis redémarrez SSH.
```
# /etc/init.d/sshd restart
```

5. Si vous êtes connecté au serveur avec SSH sur le port 22, votre connexion est alors supprimée et vous devez vous reconnecter en utilisant le nouveau port.
