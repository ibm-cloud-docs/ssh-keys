---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurando o SSH para executar em uma porta não padrão

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
