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

# Adición de una clave SSH
{: #adding-an-ssh-key}

Puede añadir claves SSH a su cuenta si es un usuario autorizado. Cada cuenta puede tener hasta 100 claves SSH en cualquier momento. Las claves SSH se utilizan con más frecuencia en el [proceso de recarga de SO](/docs/software?topic=software-reloading-the-os#reloading-the-os) y también pueden utilizarse cuando suministre un nuevo dispositivo.
{:shortdesc}

## Antes de empezar
Primero, genere la clave SSH pública, navegue hasta el menú del dispositivo y asegúrese de tener los permisos de cuenta correctos para completar las tareas.

* [Genere la clave SSH pública ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://help.github.com/articles/generating-ssh-keys){: new_window} para el dispositivo.
* Navegue hasta el menú del dispositivo de la consola. Para obtener más información, consulte [Navegación a dispositivos](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Asegúrese de tener los permisos de cuenta y el acceso al dispositivo necesarios. Solo el propietario de la cuenta, o un usuario con el permiso de la infraestructura clásica **Gestionar usuarios**, puede ajustar los permisos.

Para obtener más información sobre permisos, consulte [Permisos de la infraestructura clásica](/docs/iam?topic=iam-infrapermission#infrapermission) y [Gestión del acceso a dispositivos](/docs/vsi?topic=virtual-servers-managing-device-access).

## Adición de una clave SSH a su cuenta
Siga los siguientes pasos para añadir una clave SSH a su cuenta.

1. Desde el menú **Dispositivos**, seleccione **Gestionar > Claves SSH**.
2. Pulse **Añadir**.
3. Pulse **Examinar** para localizar el archivo de claves públicas o especifíquelo manualmente en el recuadro de texto **Contenido de la clave**.
4. Especifique un **nombre abreviado** para la clave SSH en el campo **Etiqueta**.
5. Especifique las notas aplicables en el campo **Notas**, si es necesario.
6. Pulse **Añadir** para añadir la clave SSH. 

## Pasos siguientes

Después de añadir la clave SSH, aparecerá en la lista de claves SSH. Puede [editar los detalles de claves](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key) en cualquier momento. También puede [eliminar la clave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key) de la lista. Elimine claves SSH obsoletas tan pronto como sea posible para garantizar que el espacio esté disponible si necesita añadir más claves.
