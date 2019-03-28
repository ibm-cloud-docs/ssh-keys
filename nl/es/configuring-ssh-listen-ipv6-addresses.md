---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IPv6 addresses, Linux server, IPv6

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuración de SSH para que escuche en las direcciones IPv6
{: #configuring-ssh-to-listen-on-ipv6-addresses}

Utilice el procedimiento siguiente para habilitar SSH en un servidor Linux para que escuche en IPv6:
1. Localice el archivo: /etc/ssh/sshd_config.
2. Localice la línea que contiene `ListenAddress`.
3. Elimine el comentario de la línea `#ListenAddress ::`:
```
ListenAddress ::
```

De esta manera se enlaza `sshd` con todas las direcciones de su dispositivo.
