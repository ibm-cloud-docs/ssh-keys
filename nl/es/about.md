---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Acerca de las claves SSH 

Las servidores SSH utilizan claves SSH para identificar a un usuario o dispositivo mediante la criptografía de claves públicas. Las claves SSH se componen de una combinación alfanumérica y son exclusivas del dispositivo al que están asignadas. En cualquier momento, los usuarios autorizados pueden añadir, editar o suprimir claves SSH utilizando el {{site.data.keyword.slportal_full}}.

Las claves SSH permiten el acceso a un dispositivo sin tener que utilizar una contraseña de los correspondientes clientes para cada clave pública que se haya implementado en el dispositivo. Al añadir una clave SSH a un dispositivo, que puede hacerse durante el suministro o mediante una [Recarga de SO](../software/vsi_reload_os.html), el dispositivo que se ha proporcionado con la clave SSH accede al dispositivo para la correspondiente clave sin necesidad de utilizar una contraseña. 