---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restricción del usuario root del acceso SSH
{: #restricting-the-root-user-from-ssh-access}

Cada uno de los sistemas Linux en la red de {{site.data.keyword.cloud}} tiene un usuario root con permisos. En Linux, puede crear grupos wheel, que otorgan a los usuarios permisos similares a del usuario root mediante "sudo" sin necesidad de utilizar las credenciales de usuario root. Después de crear un grupo wheel con permisos sudo de root, puede restringir el acceso SSH de los usuarios de dicho. Al restringir a los usuarios de este modo, protege el dispositivo de vulnerabilidades que pertenecen a la accesibilidad de red. Los usuarios que forman parte del grupo wheel pueden seguir realizando funciones administrativas en el dispositivo en cualquier momento.
{:shortdesc}

Siga estos pasos para restringir el usuario root del acceso SSH.

1. Abra el archivo 'etc/group' y vea si contiene una línea que defina un grupo wheel:
```
wheel:x:10:root
```

    Si esta línea no está en el archivo, créela.

2. Añada al menos un usuario a la línea de grupo wheel:
```
wheel:x:10:root, user1
```

    Los usuarios añadidos al grupo wheel tienen permisos idénticos a los del usuario root, pero utilizan su nombre de usuario exclusivo cuando acceden al sistema.
3. Ejecute el mandato `:wq` para guardar los cambios y salir del archivo.
4. Abra `/etc/ssh/sshd_config`.
5. Cambie la línea `PermitRootLogin yes` a `PermitRootLogin no`.
6. Ejecute el mandato `:wq` para guardar los cambios y salir del archivo.
7. Escriba `visudo` en la **línea de mandatos** para generar permisos de mandato.
8. Elimine la **almohadilla (#)** de la línea siguiente para descomentar la línea:
```
# %wheel ALL=(ALL) ALL
```

    **Nota:** Descomentar esta línea permite a los usuarios del grupo wheel ejecutar todos los mandatos.

9. Ejecute el mandato `:wq` para guardar los cambios y salir del archivo.
10. Ejecute el siguiente mandato en la línea de mandatos:
```
vi /etc/pam.d/su
```

11. Elimine la **almohadilla (#)** de la línea siguiente para descomentar la línea:
```
#auth required pam_wheel.so use_uid
```

    **Nota:** Si se descomenta esta línea, es necesario que los usuarios formen parte del grupo wheel para tener permiso para ejecutar todos los mandatos.
12. Ejecute el mandato `:wq` para guardar los cambios y salir del archivo.
13. Ejecute el mandato siguiente para guardar todos los cambios y reiniciar SSH:
```
# etc/init.d/ssh restart
```

## Pasos siguientes

Después de restringir el usuario root del acceso SSH, el usuario root no puede iniciar sesión en SSH. Si un usuario puede acceder actualmente al servidor a través de SSH con el usuario root, la conexión fallará después del reinicio de SSH en el procedimiento anterior. Todos los futuros intentos de conexión a SSH con el usuario root fallarán. Para revertir estos cambios, repita los pasos y cambie `PermitRootLogin` no a `PermitRootLogin` yes.
