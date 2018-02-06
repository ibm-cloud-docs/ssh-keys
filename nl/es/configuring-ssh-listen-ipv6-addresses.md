---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuración de SSH para que escuche en las direcciones IPv6

Utilice el procedimiento siguiente para habilitar IPv6 en un SSH de servidor Linux:
1. Localice el archivo: /etc/ssh/sshd_config.
2. Localice la línea que contiene `ListenAddress`.
3. Elimine el comentario de la línea `#ListenAddress ::`: 
```
ListenAddress ::
```

De esta manera se enlaza `sshd` con todas las direcciones de su dispositivo.
