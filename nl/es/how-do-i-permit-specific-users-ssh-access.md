---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: list of group name patterns, SSH access, error messages

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Concesión de acceso SSH a un usuario
{: #granting-ssh-access-to-a-user}

Siga estos pasos para otorgar acceso SSH a uno o varios usuarios. Estos pasos muestran cómo configurar este archivo:

1. Localice el siguiente archivo OpenSSH:
```
/etc/ssh/sshd_config
```

2. Realice una copia de este archivo para poder volver atrás si es necesario. Por ejemplo:
```
cp /etc/ssh/sshd_config{,.'date +%s'}
```

3. Edite el archivo utilizando las palabras clave de OpenSSH.


## Palabras clave de OpenSSH

### AllowGroups

Después de esta palabra clave, incluya una lista de patrones de nombre de grupo. Separe los patrones mediante espacios. Si especifica **Login**, sólo está permitido para los usuarios cuya lista de grupos primarios o complementarios coincida con uno de los patrones. Puede utilizar `"*" y "?"` como comodines en los patrones. Sólo son válidos los nombres de grupo; un ID de grupo numérico no se reconocerá. De forma predeterminada, **Login** está permitido para todos los grupos.

### AllowUsers

Después de esta palabra clave, incluya una lista de patrones de nombre de usuario. Separe los patrones mediante espacios. Si especifica **Login**, sólo está permitido para los nombres de usuario que coincidan con uno de los patrones. Puede utilizar `"*" y "?"` como comodines en los patrones. Sólo son válidos los nombres de usuario; un ID de grupo numérico no se reconocerá. De forma predeterminada, **Login** está permitido para todos los usuarios. Si el patrón adopta el formato USER@HOST, USER y HOST se comprobarán por separado, lo cual restringirá los inicios de sesión a determinados usuarios de hosts determinados.

### DenyGroups

Después de esta palabra clave, incluya una lista de patrones de nombre de grupo. Separe los patrones mediante espacios. Si especifica **Login**, no está permitido para los usuarios cuya lista de grupos primarios o complementarios coincida con uno de los patrones. Puede utilizar `"*" y "?"` como comodines en los patrones. Sólo son válidos los nombres de grupo; un ID de grupo numérico no se reconocerá. De forma predeterminada, **Login** está permitido para todos los grupos.

### DenyUsers

Después de esta palabra clave, incluya una lista de patrones de nombre de usuario. Separe los patrones mediante espacios. Si especifica **Login**, no está permitido para los nombres de usuario que coincidan con uno de los patrones. Puede utilizar `"*" y "?"` como comodines en los patrones. Sólo son válidos los nombres de usuario; un ID de grupo numérico no se reconocerá. De forma predeterminada, **Login** está permitido para todos los usuarios.  Si el patrón adopta el formato USER@HOST, USER y HOST se comprobarán por separado, lo cual restringirá los inicios de sesión a determinados usuarios de hosts determinados.

## Ejemplo

En el ejemplo siguiente, sólo dos usuarios específicos, `admin` y `user1` tienen permitido iniciar sesión en el servidor.
**Nota:** Puede utilizar un método similar para denegar grupos utilizando las palabras clave `DenyGroups` y `DenyUsers`.
```
AllowUsers admin user1
```

Para prepararse para la futura expansión de usuarios, puede crear un grupo en el servidor que pueda iniciar sesión en el servidor. Puede añadir usuarios individuales según sea necesario (sustituya *`username`* por el usuario real):

1. En el shell, añada un grupo de usuarios, como sshusers:
```
groupadd –r sshusers
```

2. En el shell, añada usuarios al grupo:
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. En el archivo sshd_config, otorgue acceso al grupo sshusers:
```
AllowGroups sshusers
```

4. Verifique que sshd lee la nueva configuración sin interrupciones:
```
/usr/sbin/sshd –t
```

```
echo $?
```

  Si recibe un `0` después del mandato `echo $?`, la nueva configuración es correcta.

  También puede recibir mensajes de error similares a los siguientes ejemplos:
```
sshd_config: línea 112: Opción de configuración errónea: allowuser
```

```
sshd_config: terminando, 1 opciones de configuración erróneas
```

5. Después de arreglar todos los errores y cuando tenga una configuración correcta, reinicie sshd. A continuación, se muestra un mandato de ejemplo en un sistema compatible con sysv:
  /etc/init.d/sshd restart

Asegúrese de crear una nueva sesión SSH sin desconectar la sesión existente. Verifique que puede realizar cualquier acción con los usuarios que ha añadido.
