---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurando o SSH para atender apenas em uma rede privada

É possível proteger ainda mais seu servidor executando SSHd apenas na rede de backend. Portanto, será necessário se conectar à VPN toda vez que você precisar acessar o SSH.

1. Localize o arquivo a seguir. Use este arquivo para definir o endereço IP para
`sshd`.
```
# nano /etc/ssh/sshd_config
```

2. Localize a linha que contenha `ListenAddress 0.0.0.0`. Se ela começar com um caractere
'#', remova esse caractere. Configure o endereço IP para o IP desejado para atendimento. É possível localizar
seu endereço IP interno selecionando *Hardware* no {{site.data.keyword.slportal_full}}.
3. Depois de fazer a mudança, reinicie o serviço SSH:
```
# service sshd restart
```

A janela shell atual não se desconecta quando você reinicia o serviço. Verifique se é possível
conectar-se ao servidor por meio da nova porta SSH antes de sair da sua janela shell atual. Se houver um problema, o SSHd falhará ao reiniciar e será necessário se conectar ao servidor usando um método alternativo.
