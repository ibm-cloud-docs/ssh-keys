---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restricción del acceso SSH en una red pública

La accesibilidad SSH ofrece a los usuarios la capacidad de acceder de forma segura a un dispositivo mediante una conexión a Internet. SSH está disponible en dispositivos de {{site.data.keyword.cloud}} tanto en la red pública como privada. Sin embargo, debe restringir la accesibilidad SSH en la red pública a menos que sea necesaria para una necesidad empresarial exclusiva. Al restringir el acceso SSH en la red pública, los usuarios pueden seguir accediendo a un dispositivo mediante la red privada, pero se reduce el riesgo de que usuarios desconocidos accedan al dispositivo en la red pública. Si la accesibilidad SSH en la red pública es necesaria, puede transferir SSH a un número de puerto personalizado para disponer de una capa de seguridad adicional. 
{:shortdesc}

Siga estos pasos para restringir el acceso SSH en la red pública.
1. Acceda a la **Red privada** sobre [VPN ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://www.softlayer.com/vpn-access){: new_window}.
2. Inicie sesión en el Servidor nativo **Dirección IP privada** mediante SSH.
3. Ejecute el mandato siguiente para abrir el archivo `sshd_config` y realizar ediciones:
  > `vi /etc/ssh/sshd_config`
4. Elimine la **almohadilla (#)** de la línea `ListenAddress` para eliminar el comentario de la línea.
5. Especifique la **Dirección IP privada** para el servidor dedicado en la línea `ListenAddress` de la que se ha eliminado el comentario.
6. Ejecute el mandato `:wq` para guardar los cambios y salir del archivo.
7. Reinicie el servicio sshd.
  > `service sshd restart`
8. Pruebe las actualizaciones de accesibilidad SSH intentando acceder a SSH con la dirección IP pública del servidor dedicado.<br><br><table border="1"><tr><th>Si la conexión...</th><th>Entonces...</th></tr><tr><td>No se puede realizar</td><td>Los cambios en la accesibilidad SSH se han realizado correctamente. No es necesaria ninguna otra acción.</td></tr><tr><td>Se puede realizar</td><td>Los cambios en la accesibilidad SSH no se han realizado correctamente. Repita los pasos anteriores para volver a restringir SSH. Si el problema persiste, póngase en contacto con el servicio de soporte.</td></tr></table>

## Pasos siguientes

Después de restringir el acceso SSH correctamente, los usuarios no podrán acceder al dispositivo a través de SSH si no están conectados mediante la red privada. Esta acción se puede deshacer en cualquier momento volviendo a añadir la almohadilla (#) para que la línea vuelva a ser un comentario.
