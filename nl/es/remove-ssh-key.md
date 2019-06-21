---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Eliminación de una clave SSH
{: #removing-an-ssh-key}

Cuando una clave SSH almacenada en la consola de {{site.data.keyword.cloud}} es obsoleta o ya no es necesaria, puede eliminar la clave. Elimine claves SSH tan pronto como sea posible para garantizar que haya espacio suficiente para claves válidas adicionales.
{:shortdesc}

## Antes de empezar
Primero, navegue hasta el menú del dispositivo y asegúrese de tener los permisos de cuenta correctos para completar las tareas.

* Navegue hasta el menú del dispositivo de la consola. Para obtener más información, consulte [Navegación a dispositivos](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Asegúrese de tener los permisos de cuenta y el acceso al dispositivo necesarios. Solo el propietario de la cuenta, o un usuario con el permiso de la infraestructura clásica **Gestionar usuarios**, puede ajustar los permisos.

Para obtener más información sobre permisos, consulte [Permisos de la infraestructura clásica](/docs/iam?topic=iam-infrapermission#infrapermission) y [Gestión del acceso a dispositivos](/docs/vsi?topic=virtual-servers-managing-device-access).

## Eliminación de una clave SSH

1. Desde el menú **Dispositivos**, seleccione **Gestionar > Claves SSH**.
2. Pulse el icono **Eliminar** situado al lado de la clave SSH que desee eliminar.
3. Pulse **Sí** para confirmar. 

## Pasos siguientes

Después de eliminar una clave SSH, se eliminará inmediatamente de la lista. La clave ya no puede utilizarse si se suministra un nuevo dispositivo o si se efectúa una recarga de SO en un dispositivo existente. Si la clave se elimina por error o si se debe volver a añadir a la consola de {{site.data.keyword.cloud_notm}}, consulte [Adición de una clave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key).
