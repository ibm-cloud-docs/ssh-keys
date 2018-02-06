---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# FAQ : clés SSH

## Où trouver ma clé SSH ?

Les clés SSH sont spécifiques à chaque appareil et se trouvent dans l'appareil. Comme il existe différents systèmes d'exploitation, les étapes permettant de localiser la clé SSH sont spécifiques au système d'exploitation. Pour en savoir plus sur la génération d'une clé SSH sur un appareil, consultez l'article de GitHub sur la [génération de clés SSH ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window}.

## Combien de clés SSH puis-je ajouter à mon compte ?

Vous pouvez associer jusqu'à 100 clés SSH à un compte. Les utilisateurs autorisés peuvent [ajouter 1 clé SSH](add-ssh-key.html) à la fois en utilisant le portail {{site.data.keyword.slportal_full}}. Alors que la plupart des utilisateurs n'ont pas besoin de 100 clés, vous devez supprimer les clés dont vous n'avez pas besoin pour garantir un espace suffisant pour ajouter des clés valides. Pour plus d'informations, voir la rubrique [Retrait d'une clé SSH](remove-ssh-key.html){:new_window}.

## Je ne vois pas ma clé SSH réelle, mais je vois une empreinte. Qu'est-ce que c'est ?

L'empreinte figurant avec les détails d'une clé SSH est une séquence abrégée d'octets générée par le système. L'empreinte est plus courte que la clé SSH. Elle est utilisée pour s'authentifier ou pour rechercher la clé publique correspondant à l'appareil associé.

## Si je crée ou recharge un appareil qui utilise un modèle d'image, est-ce que les clés SSH suivent ?

Oui et non. Chaque appareil dispose d'une clé SSH unique, donc la clé pour le nouvel appareil ou l'appareil rechargé sera différente de l'image.  Toutefois, les clés SSH associées à une image Flex ou à un modèle d'image standard sont associées à l'appareil lors de sa mise à disposition ou de son rechargement. Vous pouvez également ajouter des clés lors du processus de configuration. 
