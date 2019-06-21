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

# Edición de los detalles de una clave SSH
{: #editing-details-for-an-ssh-key}

Después de [añadir una clave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key) en la consola de {{site.data.keyword.cloud}}, podrá editar los detalles de la clave. Puede editar la **Etiqueta** (el nombre abreviado que se utiliza para identifica fácilmente la clave SSH) y las **Notas** para la clave.
{:shortdesc}

## Antes de empezar
Primero, navegue hasta el menú del dispositivo y asegúrese de tener los permisos de cuenta correctos para completar las tareas.

* Navegue hasta el menú del dispositivo de la consola. Para obtener más información, consulte [Navegación a dispositivos](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Asegúrese de tener los permisos de cuenta y el acceso al dispositivo necesarios. Solo el propietario de la cuenta, o un usuario con el permiso de la infraestructura clásica **Gestionar usuarios**, puede ajustar los permisos.

Para obtener más información sobre permisos, consulte [Permisos de la infraestructura clásica](/docs/iam?topic=iam-infrapermission#infrapermission) y [Gestión del acceso a dispositivos](/docs/vsi?topic=virtual-servers-managing-device-access).

## Edición de los detalles de la clave SSH

Si necesita editar la misma clave, elimine la clave y añada la clave correcta a la consola de {{site.data.keyword.cloud_notm}}. La huella dactilar que aparece con los detalles de la clave SSH no es la clave propiamente; es una breve secuencia de bytes que se utiliza en la recuperación de la clave. Es posible que la huella dactilar no represente la clave SSH real en modo alguno. 
{:note}

Siga los siguientes pasos para editar los detalles de la clave SSH.

1. Desde el menú **Dispositivos**, seleccione **Gestionar > Claves SSH**. 
2. Pulse en cualquier sitio en el campo **Etiqueta** o en el campo **Notas** para abrir el campo y editarlo.
3. Escriba el texto actualizado en el campo correspondiente.
4. Pulse en cualquier lugar de la pantalla para cerrar el campo y no hacer más cambios.


## Pasos siguientes

Los detalles de las claves SSH que se han editado se actualizan inmediatamente en la lista de claves SSH.
