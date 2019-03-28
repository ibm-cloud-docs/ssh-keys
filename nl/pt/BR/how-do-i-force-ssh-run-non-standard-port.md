---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurando o SSH para executar em uma porta não padrão
{: #configuring-ssh-to-run-on-a-non-standard-port}

Siga estas etapas para forçar o SSH a executar em uma porta não padrão:

1. Abra /etc/ssh/sshd_config em um editor de texto. O exemplo a seguir é para o editor de vi.
```
# vi /etc/ssh/sshd_config
```

2. Navegue até a linha a seguir:
```
# Port 22
```

3. Remova o comentário e edite essa linha para refletir a nova porta.
```
Port 2255
```
(isso pode ser configurado para qualquer porta não padrão)

4. Salve e saia do arquivo e reinicie o SSH.
```
# /etc/init.d/sshd restart
```

5. Se você estiver conectado ao servidor usando o SSH na porta 22, sua conexão cairá e será necessário
reconectar-se usando a nova porta.
