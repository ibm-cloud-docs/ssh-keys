---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Ajout d'une clé SSH
{: #adding-an-ssh-key}

Vous pouvez ajouter des clés SSH à votre compte si vous êtes un utilisateur autorisé. Chaque compte peut comptabiliser jusqu'à 100 clés SSH à tout moment. Dans le portail {{site.data.keyword.slportal_full}}, les clés SSH sont le plus souvent utilisées dans le [processus de rechargement de système d'exploitation](/docs/infrastructure/software?topic=software-reloading-the-os) et peuvent également être utilisées lors de la mise à disposition d'un nouvel appareil.

**Remarque :** [Générez la clé SSH publique ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://help.github.com/articles/generating-ssh-keys){: new_window} avec l'appareil pour lequel vous ajoutez une clé avant d'ajouter une clé SSH dans votre compte.

Suivez cette procédure pour ajouter une clé SSH à votre compte.
1. Accédez à l'écran **Clés SSH**. Consultez la rubrique [Initiation aux clés SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial).
2. Cliquez sur **Ajouter**.
3. Cliquez sur **Parcourir** pour localiser le fichier de clé publique ou entrez-le manuellement dans la zone de texte **Contenu de la clé**.
4. Entrez un **nom abrégé** pour la clé SSH dans la zone **Libellé**.
5. Indiquez toute remarque applicable dans la zone **Remarques**, si nécessaire.
6. Cliquez sur **Ajouter** pour ajouter la clé SSH. Cliquez sur **Annuler** pour annuler l'action.

## Etapes suivantes

Après avoir ajouté la clé SSH, elle apparaît dans la liste des clés SSH.
Vous pouvez [éditer les détails de la clé](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key) à tout moment. Vous pouvez également [retirer la clé SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key) de la liste. Retirez les clés SSH obsolètes dès que possible pour vous assurer de disposer d'espace disponible si vous devez ajouter des clés supplémentaires.
