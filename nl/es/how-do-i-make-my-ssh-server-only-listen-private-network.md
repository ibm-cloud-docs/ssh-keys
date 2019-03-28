---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuración de SSH para que se escuche solo en una red privada
{: #configuring-ssh-to-listen-only-on-a-private-network}

Puede proteger el servidor ejecutando SSHd sólo en la red de fondo. Por lo tanto, debe conectarse a la VPN cada vez que necesite acceder a SSH.

1. Localice el archivo siguiente. Utilice este archivo para definir la dirección de IP para `sshd`.
```
# nano /etc/ssh/sshd_config
```

2. Localice la línea que contiene `ListenAddress 0.0.0.0`. Si empieza con un carácter '#', elimine este carácter. Establezca la dirección IP en la dirección IP en la que desea que escuche. Para encontrar la dirección IP interna, seleccione *Hardware* en {{site.data.keyword.slportal_full}}.
3. Después de realizar el cambio, reinicie el servicio SSH:
```
# service sshd restart
```

La ventana de shell actual no se desconectará cuando se reinicie el servicio. Verifique que puede conectarse al servidor a través del nuevo puerto SSH nueva antes de salir de la ventana de shell actual. Si hay algún problema, SSHd no se reiniciará y deberá conectarse al servidor mediante un método alternativo.
