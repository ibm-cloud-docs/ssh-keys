---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Preguntas frecuentes: Claves SSH

## ¿Dónde puedo encontrar mi clave SSH?

Las claves SSH son específicas del dispositivo y se encuentra en el dispositivo. Puesto que cada sistema operativo es diferente, los pasos para localizar la clave SSH serán específicos del sistema operativo. Para obtener más información sobre cómo generar una clave SSH en un dispositivo, consulte el artículo de GitHub sobre la [generación de SSH ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window}.

## ¿Cuántas claves SSH puedo añadir a mi cuenta?

Puede asociar un máximo de 100 claves SSH a una cuenta. Los usuarios autorizados pueden [añadir 1 clave SSH](add-ssh-key.html) en un momento determinado utilizando {{site.data.keyword.slportal_full}}. Aunque la mayoría de los usuarios no necesitan 100 claves, debe eliminar las claves que no necesite para asegurarse de que haya espacio disponible para obtener más claves válidas. Para obtener más información, consulte [Eliminación de claves SSH](remove-ssh-key.html){:new_window}.

## No veo mi clave SSH en la lista, en cambio veo una huella dactilar. ¿Qué significa?

La huella dactilar que se muestra con los detalles para una clave SSH es una secuencia de bytes abreviada generada por el sistema. La huella dactilar es más corta que la propia clave SSH y se utiliza para autenticarse o para buscar la clave pública para el dispositivo asociado. 

## Si creo o recargo un dispositivo que utiliza una plantilla de imagen, ¿se conservarán las claves SSH?

Sí y no. Cada dispositivo tiene una clave SSH exclusiva, de modo que la clave del dispositivo recién suministrado o cargado será distinta a la de la imagen. Sin embargo, las claves SSH que están asociadas con una imagen Flex o una plantilla de imagen estándar están asociadas con el dispositivo cuando se suministra o se carga. También puede añadir claves durante el proceso de configuración.
