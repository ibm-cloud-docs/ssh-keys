---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurando o SSH para atender endereços IPv6

Use o procedimento a seguir para ativar o IPv6 em um SSH do servidor Linux:
1. Localize o arquivo: /etc/ssh/sshd_config.
2. Localize a linha que contém `ListenAddress`.
3. Remova o comentário da linha `#ListenAddress ::`:
```
ListenAddress ::
```

Isso une `sshd` a cada endereço em seu dispositivo.
