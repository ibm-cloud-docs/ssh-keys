---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurando o SSH para atender endereços IPv6

Use o procedimento a seguir para ativar o SSH em um servidor Linux para atender no IPv6:
1. Localize o arquivo: /etc/ssh/sshd_config.
2. Localize a linha que contém `ListenAddress`.
3. Remova o comentário da linha `#ListenAddress ::`:
```
ListenAddress ::
```

Isso une `sshd` a cada endereço em seu dispositivo.
