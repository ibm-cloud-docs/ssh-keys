---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connexion à un serveur Red Hat avec SSH

Pour finaliser cette procédure, vous avez besoin d'un client SSH, tel que PuTTY, sur votre ordinateur personnel. PuTTY est un client SSH gratuit largement répandu.
Dans la plupart des cas, vous pouvez utiliser les options par défaut de PuTTY pour parvenir à vous connecter pour la première fois à votre serveur Red Hat.

1. Ouvrez PuTTY et entrez l'adresse IP principale de votre serveur dans la zone `'Hostname (or IP address)'` et cliquez sur Open.
  Remarque : Le port par défaut de SSH est 22, mais vous pouvez le modifier sur le serveur une fois votre première connexion établie.
2. Le serveur Red Hat vous invite à entrer un nom d'utilisateur et un mot de passe. Entrez vos informations d'utilisateur root et de mot de passe pour le serveur.
3. Sauvegardez les détails de la connexion (adresse IP et port) dans les sessions en entrant l'adresse IP et le port. Créez un titre pour ces propriétés de connexion par exemple "Mon serveur" et cliquez sur Save.
  Lorsque vous vous connectez à votre serveur, vous devez mettre en évidence uniquement la connexion sauvegardée et cliquer sur Open.

Vous pouvez vous connecter à votre serveur en utilisant le réseau public.
Vous pouvez également vous connecter en utilisant le réseau privé. Suivez les instructions indiquées dans le portail {{site.data.keyword.slportal_full}} sur la connexion au réseau privé virtuel (VPN) puis utilisez SSH pour vous connecter à votre adresse IP privée.
