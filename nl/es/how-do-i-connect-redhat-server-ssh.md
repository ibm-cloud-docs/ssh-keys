---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Conexión a un servidor RedHat con SSH

Para completar este procedimiento, necesita un cliente SSH, como por ejemplo, PuTTY, en su sistema personal. PuTTY es un cliente SSH gratuito y ampliamente distribuido.
En la mayoría de los casos, puede utilizar las opciones predeterminadas en PuTTY para conectarse correctamente a su servidor RedHat la primera vez.

1. Abra PuTTY y escriba en la dirección IP principal de su servidor en el campo `'Hostname (o IP address)'` y pulse Abrir.
  Nota: El puerto predeterminado de SSH es 22, pero puede cambiarlo en el servidor después de la primera conexión satisfactoria.
2. El servidor RedHat le solicita un nombre de usuario y la contraseña. Escriba la información de usuario root y la contraseña del servidor.
3. Guarde los detalles de la conexión (dirección IP y puerto) en Sesiones escribiendo la dirección IP y el puerto. Cree un título para las propiedades de conexión, como por ejemplo, "Mi Servidor" y pulse Guardar.
  Cuando se conecte a su servidor, deberá resaltar sólo la sesión guardada y pulsar Abrir.

Puede conectarse a su servidor utilizando la red pública.
También puede conectarse utilizando la red privada. Siga las instrucciones de {{site.data.keyword.slportal_full}} para conectarse a la VPN y, a continuación, utilizar la SSH para conectarse a su dirección IP privada.
