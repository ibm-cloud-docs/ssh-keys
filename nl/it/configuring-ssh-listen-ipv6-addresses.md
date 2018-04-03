---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurazione di SSH per ascoltare gli indirizzi IPv6

Utilizza la seguente procedura per abilitare SSH su un server Linux per essere in ascolto su IPv6:
1. Individua il file: /etc/ssh/sshd_config.
2. Individua la riga che contiene `ListenAddress`.
3. Annulla il comment nella riga `#ListenAddress ::`:
```
ListenAddress ::
```

Questo associa `sshd` ad ogni indirizzo sul tuo dispositivo.
