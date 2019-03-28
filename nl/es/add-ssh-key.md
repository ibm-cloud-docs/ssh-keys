---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Adición de una clave SSH
{: #adding-an-ssh-key}

Puede añadir claves SSH a su cuenta si es un usuario autorizado. Cada cuenta puede tener hasta 100 claves SSH en cualquier momento. En {{site.data.keyword.slportal_full}}, las claves SSH se utilizan con más frecuencia en el [proceso de recarga de SO](/docs/infrastructure/software?topic=software-reloading-the-os) y también pueden utilizarse cuando suministre un nuevo dispositivo.

**Nota:** [Generar la clave SSH pública ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://help.github.com/articles/generating-ssh-keys){: new_window} con el dispositivo para el que está añadiendo una clave antes de añadir una clave SSH a su cuenta.

Siga estos pasos para añadir una clave SSH a su cuenta.
1. Acceda a la pantalla de **Claves SSH**. Consulte [Iniciación a las claves SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial).
2. Pulse **Añadir**.
3. Pulse **Examinar** para localizar el archivo de claves públicas o especifíquelo manualmente en el recuadro de texto **Contenido de la clave**.
4. Especifique un **nombre abreviado** para la clave SSH en el campo **Etiqueta**.
5. Especifique las notas aplicables en el campo **Notas**, si es necesario.
6. Pulse **Añadir** para añadir la clave SSH. Pulse **Cancelar** para cancelar la acción.

## Pasos siguientes

Después de añadir la clave SSH, aparecerá en la lista de claves SSH.
Puede [editar los detalles de claves](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key) en cualquier momento. También puede [eliminar la clave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key) de la lista. Elimine claves SSH obsoletas tan pronto como sea posible para garantizar que el espacio esté disponible si necesita añadir más claves.
