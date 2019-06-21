---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Retrait d'une clé SSH
{: #removing-an-ssh-key}

Lorsqu'une clé SSH stockée sur la console {{site.data.keyword.cloud}} est obsolète ou n'est plus requise, vous pouvez la retirer. Retirez les clés SSH obsolètes dès que possible pour vous assurer de disposer d'un espace suffisant pour ajouter des clés valides supplémentaires.
{:shortdesc}

## Avant de commencer
Tout d'abord, naviguez jusqu'au menu de l'appareil et assurez-vous d'avoir les autorisations de compte appropriées pour effectuer les tâches.

* Accédez au menu de votre console. Pour plus d'informations, voir [Navigating to devices](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Vérifiez que vous disposez des autorisations de compte nécessaires et que vous avez accès aux appareils. Seul le propriétaire du compte, ou un utilisateur avec l'autorisation **Gérer les utilisateurs** de l'infrastructure classique, peut régler les autorisations. 

Pour plus d'informations sur les autorisations, voir [Droits d'infrastructure classique](/docs/iam?topic=iam-infrapermission#infrapermission) et [Gestion de l'accès aux terminaux](/docs/vsi?topic=virtual-servers-managing-device-access).

## Procédure de retrait d'une clé SSH

1. Dans le menu **Equipements**, sélectionnez **Gérer > Clés SSH**.
2. Cliquez sur l'icône **Retirer** en regard de la clé SSH que vous voulez retirer.
3. Cliquez sur **Oui** pour confirmer. 

## Etapes suivantes

Une fois la clé SSH retirée, elle est immédiatement supprimée de la liste. La clé ne peut plus être utilisée en cas de mise à disposition d'un nouvel appareil ou lorsque vous effectuez un rechargement de système d'exploitation sur un appareil existant. Si la clé est supprimée par erreur ou doit à nouveau être ajoutée à la console {{site.data.keyword.cloud_notm}}, voir [Ajout d'une clé SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key).
