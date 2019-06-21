---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-06"

keywords: SSH keys, remote host authentication SSH keys, public-key cryptography

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Generación y uso de claves SSH para la autenticación de host remoto
{: #generating-and-using-ssh-keys-for-remote-host-authentication}

Las claves SSH son una forma de identificarse en un servidor SSH que utilice la criptografía de claves públicas y la autenticación de respuesta de verificación de identidad. Una ventaja inmediata de este método en comparación con la autenticación de contraseñas tradicional es que el servidor puede autenticarlo sin necesidad de enviar la contraseña por la red. También puede utilizarlo con la automatización, ya que permite la comunicación con el servidor de forma desatendida.

## Generación de claves SSH en Linux

Para generar una clave SSH en el servidor Linux ejecute el mandato `ssh-keygen`. El mandato puede utilizar distintivos si desea personalizar el tipo de clave que se genera, así como los algoritmos de firma utilizados para generar la clave. Este ejemplo genera una clave RSA de 2048 bits estándar sin frase de contraseña. El mandato le pedirá la ubicación en la que desea almacenar la clave (el valor predeterminado es $HOME/.ssh/), así como una frase de contraseña para proteger la clave SSH.

    root@bck2:/etc# ssh-keygen
    Generating public/private rsa key pair.
    Enter file in which to save the key (/root/.ssh/id_rsa):
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in /root/.ssh/id_rsa.
    Your public key has been saved in /root/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx root@bck2.example.com
    The key's randomart image is:
    +---[RSA 2048]----+
    |.  oo*%=+o..     |
    |.++.oX+=. .      |
    |..+ooo=. .       |
    |   E.+. .o.      |
    |    +   S..+     |
    |     . +. =      |
    |      o  = o     |
    |      .o+ +      |
    |       +o.       |
    +----[SHA256]-----+

## Copia de la clave pública en los hosts remotos

Para autenticar un host remoto utilizando una clave SSH pública utilizará el mandato `ssh-copy-id`. Utilice el distintivo `-i` para especificar la clave pública que va a copiar en el host remoto.

    root@bck2: # ssh-copy-id -i /root/.ssh/id_rsa.pub root@10.176.18.15
    /usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/root/.ssh/id_rsa.pub"
    The authenticity of host '10.176.18.15 (10.176.18.15)' can't be established.
    ECDSA key fingerprint is SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.

    Are you sure you want to continue connecting (yes/no)? yes
    /usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
    /usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
    root@10.176.18.15's password:

    Number of key(s) added: 1

    Now try logging into the machine, with:   "ssh 'root@10.176.18.15'"
    and check to make sure that only the key(s) you wanted were added.

El mandato ssh-copy-id añade las claves al archivo .ssh/authorized_key del host remoto.
{:note}

## Prueba de que la clave se ha copiado correctamente

Para probar si la clave pública se ha copiado correctamente al host remoto, ejecute ssh en el host remoto.

    root@bck2:/etc# ssh root@10.176.18.15
    Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * Documentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/advantage

      Get cloud support with Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

Como puede ver, no se solicita contraseña al ejecutar ssh en el host remoto.

## Claves SSH con una frase de contraseña

Proporcionar una frase de contraseña para la clave SSH proporciona una capa adicional de seguridad, pero también puede causar problemas al intentar ejecutar scripts automatizados que requieran el uso de la clave protegida.

ssh-agent puede gestionar las claves por usted. Sólo debe especificar la frase de contraseña una vez. ssh-agent conserva la clave en su memoria y la recupera cuando es necesaria. Para que ssh-agent gestione sus claves, emita el siguiente mandato:

    eval $(ssh-agent)

Cuando el programa empiece a utilizar el mandato ssh-add para añadir su clave pública al agente, el programa de utilidad ssh-add busca nombres de clave predeterminados, los cuales incluyen id_rsa, y los añade a ssh-agent. Después de escribir la contraseña, la clave "desbloqueada" se almacena con ssh-agent y se puede utilizar para autenticarse en otros servidores.

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

Cada vez que abra una nueva sesión de terminal, se le solicitará la frase de contraseña de la clave. Considere la posibilidad de ejecutar los siguientes mandatos para añadir su archivo `.bash_profile` para que ssh-agent se inicie con cada sesión bash y se añada su clave.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
