---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurazione di SSH per l'esecuzione su una porta non standard

Segui questa procedura per forzare l'esecuzione di SSH su una porta non standard:

1. Apri /etc/ssh/sshd_config in un editor di testo. Il seguente esempio è per l'editor vi.
```
# vi /etc/ssh/sshd_config
```
 
2. Passa alla seguente riga:
```
# Port 22
```
 
3. Annulla il comment e modifica questa riga per rispecchiare la nuova porta.
```
Port 2255
``` 
(questa può essere impostata su una qualsiasi porta non standard)
 
4. Salva e esci dal file, e riavvia SSH.
```
# /etc/init.d/sshd restart
```

5. Se sei collegato al server utilizzando SSH sulla porta 22, la tua connessione cadrà e dovrai ricollegarti utilizzando la nuova porta.
