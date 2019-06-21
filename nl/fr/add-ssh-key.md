---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Ajout d'une clé SSH
{: #adding-an-ssh-key}

Vous pouvez ajouter des clés SSH à votre compte si vous êtes un utilisateur autorisé. Chaque compte peut posséder jusqu'à 100 clés SSH à tout moment. Les clés SSH sont le plus souvent utilisées dans le [processus de rechargement du système d'exploitation](/docs/software?topic=software-reloading-the-os#reloading-the-os) et peuvent également être utilisées lorsque vous mettez à disposition un nouvel appareil.
{:shortdesc}

## Avant de commencer
Tout d'abord, générez votre clé publique SSH, naviguez jusqu'au menu de l'appareil et assurez-vous d'avoir les autorisations de compte appropriées pour effectuer les tâches.

* [Générez la clé SSH publique ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://help.github.com/articles/generating-ssh-keys){: new_window} pour votre appareil.
* Accédez au menu de votre console. Pour plus d'informations, voir [Navigating to devices](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Vérifiez que vous disposez des autorisations de compte nécessaires et que vous avez accès aux appareils. Seul le propriétaire du compte, ou un utilisateur avec l'autorisation **Gérer les utilisateurs** de l'infrastructure classique, peut régler les autorisations. 

Pour plus d'informations sur les autorisations, voir [Droits d'infrastructure classique](/docs/iam?topic=iam-infrapermission#infrapermission) et [Gestion de l'accès aux terminaux](/docs/vsi?topic=virtual-servers-managing-device-access).

## Ajout d'une clé SSH à votre compte
Suivez la procédure décrite ci-dessous pour ajouter une clé SSH à votre compte.

1. Dans le menu **Equipements**, sélectionnez **Gérer > Clés SSH**.
2. Cliquez sur **Ajouter**.
3. Cliquez sur **Parcourir** pour localiser le fichier de clé publique ou entrez-le manuellement dans la zone de texte **Contenu de la clé**.
4. Entrez un **nom abrégé** pour la clé SSH dans la zone **Libellé**.
5. Indiquez toute remarque applicable dans la zone **Remarques**, si nécessaire.
6. Cliquez sur **Ajouter** pour ajouter la clé SSH. 

## Etapes suivantes

Après avoir ajouté la clé SSH, elle apparaît dans la liste des clés SSH. Vous pouvez [éditer les détails de la clé](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key) à tout moment. Vous pouvez également [retirer la clé SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key) de la liste. Retirez les clés SSH obsolètes dès que possible pour vous assurer que de l'espace est disponible si vous devez ajouter d'autres clés.
