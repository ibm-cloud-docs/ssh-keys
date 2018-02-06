---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restriction de l'accès SSH sur un réseau public

L'accessibilité SSH fournit aux utilisateurs la possibilité d'accéder en toute sécurité à un appareil via une connexion Internet. SSH est disponible sur les appareils {{site.data.keyword.cloud}} sur le réseau public et privé. Toutefois, vous devez restreindre l'accessibilité de SSH sur le réseau public, sauf en cas de nécessité pour un besoin d'entreprise unique. En restreignant l'accès SSH sur le réseau public, les utilisateurs peuvent toujours accéder à un appareil via le réseau privé, mais les risques liés à l'accès potentiel d'utilisateurs inconnus à l'appareil sur le réseau public sera atténué. Si l'accessibilité SSH via le réseau public est nécessaire, il est recommandé de transférer SSH sur un numéro de port personnalisé pour ajouter une couche de sécurité supplémentaire.
{:shortdesc}

Suivez cette procédure pour limiter l'accès SSH sur le réseau public.
1. Accédez au **Réseau privé** via le réseau [VPN ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://www.softlayer.com/vpn-access){: new_window}.
2. Connectez-vous à l'**Adresse IP privée** du serveur bare metal via SSH.
3. Exécutez la commande suivante pour ouvrir le fichier `sshd_config` en mode édition :
  > `vi /etc/ssh/sshd_config`
4. Supprimez le signe **dièse (#)** d'une ligne `ListenAddress` pour supprimer la mise en commentaire de cette ligne.
5. Entrez l'**adresse IP privée** du serveur bare metal sur la ligne `ListenAddress` dont vous avez supprimé la mise en commentaire.
6. Exécutez la commande `:wq` pour sauvegarder les modifications et quitter le fichier.
7. Redémarrez le service sshd
  > `service sshd restart`
8. Testez les mises à jour de l'accessibilité SSH en essayant d'accéder à SSH via l'adresse IP publique du serveur bare metal.<br><br><table border="1"><tr><th>Si une connexion...</th><th>Alors...</th></tr><tr><td>Ne peut pas être établie</td><td>Les modifications effectuées à l'accessibilité SSH ont été prises en compte. Aucune autre action n'est requise.</td></tr><tr><td>Peut être établie</td><td>Les modifications apportées à l'accessibilité SSH n'ont pas été prises en compte. Répétez les étapes ci-dessus pour limiter l'accès SSH. Si les problèmes persistent, veuillez [contacter le support](https://control.softlayer.com/).</td></tr></table>

## Etapes suivantes

Après restriction de l'accès SSH, les utilisateurs ne pourront pas accéder à l'appareil via SSH s'ils ne se connectent pas via le réseau privé. Cette action peut être annulée à tout moment en ajoutant le signe dièse (#) au début de la ligne pour lui rendre son statut de commentaire.
