---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH key, key details, IBM Cloud infrastructure customer

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Edition des détails d'une clé SSH
{: #editing-details-for-an-ssh-key}

Après avoir [ajouté une clé SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key) dans la console {{site.data.keyword.cloud}}, vous pouvez éditer les détails de la clé. Vous pouvez modifier les zones **Libellé** (nom abrégé utilisé pour identifier facilement la clé SSH) et **Remarques** de la clé.
{:shortdesc}

## Avant de commencer
Tout d'abord, naviguez jusqu'au menu de l'appareil et assurez-vous d'avoir les autorisations de compte appropriées pour effectuer les tâches.

* Accédez au menu de votre console. Pour plus d'informations, voir [Navigating to devices](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Vérifiez que vous disposez des autorisations de compte nécessaires et que vous avez accès à l'appareil. Seul le propriétaire du compte, ou un utilisateur avec l'autorisation **Gérer les utilisateurs** de l'infrastructure classique, peut régler les autorisations. 

Pour plus d'informations sur les autorisations, voir [Droits d'infrastructure classique](/docs/iam?topic=iam-infrapermission#infrapermission) et [Gestion de l'accès aux terminaux](/docs/vsi?topic=virtual-servers-managing-device-access).

## Edition des détails des clés SSH

Si vous devez éditer la clé elle-même, retirez la clé et ajoutez la clé correcte à la console {{site.data.keyword.cloud_notm}}. L'empreinte digitale qui est répertoriée avec les détails de la clé SSH n'est pas la clé elle-même ; il s'agit d'une courte séquence d'octets utilisée pour l'extraction de la clé. L'empreinte ne peut en aucune façon représenter la clé SSH réelle.
{:note}

Effectuez les étapes suivantes pour éditer les détails d'une clé SSH.

1. Dans le menu **Equipements**, sélectionnez **Gérer > Clés SSH**. 
2. Cliquez n'importe où dans la zone **Libellé** ou **Remarques** pour ouvrir la zone en mode édition.
3. Entrez le texte mis à jour dans la zone correspondante.
4. Cliquez n'importe où sur l'écran pour fermer la zone et effectuer d'autres modifications.


## Etapes suivantes

Les détails de la clé SSH modifiés sont mis à jour immédiatement dans la liste des clés SSH.
