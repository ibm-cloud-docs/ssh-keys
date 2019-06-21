---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restriction de l'accès SSH pour l'utilisateur root
{: #restricting-the-root-user-from-ssh-access}

Tout système Linux sur le réseau {{site.data.keyword.cloud}} a un utilisateur root doté de droits d'administration. Sous Linux, vous pouvez créer des groupes 'wheel', qui octroient aux utilisateurs des droits similaires à ceux de l'utilisateur root via la commande "sudo" sans nécessiter l'utilisation des données d'identification de l'utilisateur root. Après avoir créé un groupe wheel avec les droits sudo sur l'utilisateur root, vous pouvez refuser l'accès SSH aux utilisateurs figurant dans ce groupe. En limitant l'accès utilisateur ainsi, vous protégez l'appareil des vulnérabilités en matière de sécurité liées à l'accessibilité au réseau. Les utilisateurs faisant partie du groupe wheel peuvent toujours effectuer des fonctions d'administration sur l'appareil à tout moment.
{:shortdesc}

Suivez cette procédure pour empêcher l'accès SSH à l'utilisateur root.

1. Ouvrez le fichier 'etc/group' et vérifiez s'il contient une ligne qui définit un groupe wheel :
```
wheel:x:10:root
```

    Si cette ligne ne figure pas dans le fichier, créez-la.

2. Ajoutez au moins un utilisateur (user1) dans la ligne du groupe wheel :
```
wheel:x:10:root, user1
```

    Les utilisateurs ajoutés dans le groupe wheel ont des droits identiques à ceux de l'utilisateur root, mais ils utilisent leur nom d'utilisateur unique pour accéder au système.
3. Exécutez la commande `:wq` pour sauvegarder les modifications et quitter le fichier.
4. Ouvrez le fichier `/etc/ssh/sshd_config`.
5. Remplacez la ligne `PermitRootLogin yes` par `PermitRootLogin no`.
6. Exécutez la commande `:wq` pour sauvegarder les modifications et quitter le fichier.
7. Entrez `visudo` sur la **ligne de commande** pour générer les droits sur les commandes.
8. Supprimez le signe **dièse (#)** de la ligne suivante pour supprimer la mise en commentaire de la ligne :
```
# %wheel ALL=(ALL) ALL
```

   La suppression de la mise en commentaire de cette ligne permet aux utilisateurs du groupe wheel d'exécuter toutes les commandes.
   {:note}

9. Exécutez la commande `:wq` pour sauvegarder les modifications et quitter le fichier.
10. Exécutez la commande suivante sur la ligne de commande :
```
vi /etc/pam.d/su
```

11. Supprimez le signe **dièse (#)** de la ligne suivante pour supprimer la mise en commentaire de la ligne :
```
#auth required pam_wheel.so use_uid
```

   La suppression de la mise en commentaire de cette ligne nécessite que les utilisateurs fassent partie du groupe wheel pour avoir le droit d'exécuter toutes les commandes.
   {:note}
   
12. Exécutez la commande `:wq` pour sauvegarder les modifications et quitter le fichier.
13. Exécutez la commande suivante pour sauvegarder toutes les modifications et redémarrer SSH :
```
# etc/init.d/ssh restart
```

## Etapes suivantes

Après avoir retiré l'accès SSH à l'utilisateur root, cet utilisateur ne peut plus se connecter à SSH. Si un utilisateur a accès au serveur via SSH en tant qu'utilisateur root, la connexion échouera au redémarrage de SSH effectué lors de la procédure précédente. Toutes les tentatives de connexion ultérieures à SSH via l'utilisateur root échoueront. Pour annuler ces modifications, répétez la procédure en remplaçant `PermitRootLogin` no par `PermitRootLogin` yes.
