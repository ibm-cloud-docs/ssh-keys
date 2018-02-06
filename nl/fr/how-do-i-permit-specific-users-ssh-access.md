---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Octroi d'accès SSH à un utilisateur 

Suivez cette procédure pour octroyer l'accès SSH à un ou plusieurs utilisateurs. Les étapes suivantes montrent comment configurer ce fichier :

1. Localisez le fichier OpenSSH suivant :
```
/etc/ssh/sshd_config
```
  
2. Effectuez une sauvegarde de ce fichier de sorte à pouvoir le récupérer si nécessaire. Par exemple :
```
cp /etc/ssh/sshd_config{,.'date +%s'}
```
  
3. Editez le fichier en utilisant les mots clés OpenSSH.


## Mots clés OpenSSH

### AllowGroups 

Après ce mot clé, insérez une liste de masques de nom de groupe. Séparez les masques par des espaces. Si vous indiquez **Login**, la connexion n'est autorisée que pour les utilisateurs dont le groupe principal ou la liste de groupes supplémentaires correspond à l'un des masques. Vous pouvez utiliser `"*" et "?"` comme caractères génériques dans les masques. Seuls les noms de groupe sont valides. Un ID de groupe numérique n'est pas reconnu. Par défaut, la connexion est autorisée pour tous les groupes.

### AllowUsers 

Après ce mot clé, insérez une liste de masques de nom d'utilisateur. Séparez les masques par des espaces. Si vous indiquez **Login**, la connexion n'est autorisée que pour les noms d'utilisateur correspondant à l'un des masques. Vous pouvez utiliser `"*" et "?"` comme caractères génériques dans les masques. Seuls les noms d'utilisateur sont valides. Un ID utilisateur numérique n'est pas reconnu. Par défaut, la connexion est autorisée pour tous les utilisateurs. Si le masque prend la forme USER@HOST, l'utilisateur (USER) et l'hôte (HOST) sont vérifiés séparément, limitant les connexions à certains utilisateurs sur certains hôtes.

### DenyGroups 

Après ce mot clé, insérez une liste de masques de nom de groupe. Séparez les masques par des espaces. Si vous indiquez **Login**, la connexion est interdite aux utilisateurs dont le groupe principal ou la liste de groupes supplémentaires correspond à l'un des masques. Vous pouvez utiliser `"*" et "?"` comme caractères génériques dans les masques. Seuls les noms de groupe sont valides. Un ID de groupe numérique n'est pas reconnu. Par défaut, la connexion est autorisée pour tous les groupes.

### DenyUsers 

Après ce mot clé, insérez une liste de masques de nom d'utilisateur. Séparez les masques par des espaces. Si vous indiquez **Login**, la connexion est interdite aux noms d'utilisateur correspondant à l'un des masques. Vous pouvez utiliser `"*" et "?"` comme caractères génériques dans les masques. Seuls les noms d'utilisateur sont valides. Un ID utilisateur numérique n'est pas reconnu. Par défaut, la connexion est autorisée pour tous les utilisateurs. Si le masque prend la forme USER@HOST, l'utilisateur (USER) et l'hôte (HOST) sont vérifiés séparément, limitant les connexions à certains utilisateurs sur certains hôtes.

## Exemple

Dans l'exemple suivant, seuls deux utilisateurs, `admin` et `user1`, sont autorisés à se connecter au serveur.
**Remarque :** Vous pouvez utiliser une méthode similaire pour refuser des groupes en utilisant les mots clés `DenyGroups` et `DenyUsers`.
```
AllowUsers admin user1
```

Pour préparer l'extension à d'autres utilisateurs, vous pouvez créer un groupe sur le serveur pouvant se connecter au serveur. Vous pouvez ajouter des utilisateurs individuels lorsque vous en avez besoin (remplacez *`username`* par l'utilisateur réel) :

1. Dans l'interpréteur de commandes, ajoutez un groupe d'utilisateurs, par exemple 'sshusers' :
```
groupadd –r sshusers
```

2. Dans l'interpréteur de commandes, ajoutez des utilisateurs (admin, user1) dans le groupe :
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. Dans le fichier sshd_config, autorisez l'accès au groupe sshusers :
```
AllowGroups sshusers
```

4. Vérifiez que sshd lit la nouvelle configuration sans interruption :
```
/usr/sbin/sshd –t
```

```
echo $?
```

  Si vous obtenez `0` à la suite de la commande `echo $?`, la nouvelle configuration est correcte.

  Vous pouvez également obtenir des messages d'erreur indiquant une mauvaise configuration, comme par exemple :
```
sshd_config: line 112: Bad configuration option: allowuser
```

```
sshd_config: terminating, 1 bad configuration options
```

5. Après avoir résolu toutes les erreurs et obtenu une configuration correcte, redémarrez sshd. L'exemple de commande suivant concerne un système compatible avec SysV :
  /etc/init.d/sshd restart

Assurez-vous de créer une nouvelle session SSH sans vous déconnecter de votre session existante. Vérifiez que vous pouvez effectuer toutes les actions avec les utilisateurs que vous avez ajoutés.
