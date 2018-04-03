---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuración de SSH para se ejecute en un puerto no estándar

Siga estos pasos para forzar a SSH para que se ejecute en un puerto no estándar:

1. Abra /etc/ssh/sshd_config en un editor de texto. El ejemplo siguiente es para el editor vi.
```
# vi /etc/ssh/sshd_config
```
 
2. Vaya a la línea siguiente:
```
# Port 22
```
 
3. Elimine el comentario de la línea y edítela para reflejar el nuevo puerto.
```
Port 2255
``` 
(se puede establecer en cualquier puerto no estándar)
 
4. Guarde y salga del archivo y reinicie SSH.
```
# /etc/init.d/sshd restart
```

5. Si está conectado al servidor utilizando SSH en el puerto 22, la conexión caerá y deberá volver a conectar utilizando el puerto nuevo.
