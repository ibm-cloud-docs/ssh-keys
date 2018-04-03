---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Concedendo acesso SSH a um usuário 

Siga estas etapas para conceder acesso SSH a um ou mais usuários. Estas etapas demonstram como
configurar esse arquivo:

1. Localize o arquivo OpenSSH a seguir:
```
/etc/ssh/sshd_config
```
  
2. Faça backup desse arquivo para que possa ser revertido, se necessário. Por exemplo:
```
cp /etc/ssh/sshd_config{,.'date +%s'}
```
  
3. Edite o arquivo usando as palavras-chave do OpenSSH.


## Palavras-chave do OpenSSH

### AllowGroups 

Após essa palavra-chave, inclua uma lista de padrões de nome de grupo. Separe os padrões com espaços. Se
você especificar **Login**, será permitido apenas para usuários cujo grupo primário ou
grupo complementar corresponde a um dos padrões. É possível usar `"*" e "?"` como curingas nos padrões. Apenas nomes de grupo são válidos; um ID do grupo numérico não é reconhecido. Por
padrão, **Login** é permitido para todos os grupos.

### AllowUsers 

Após essa palavra-chave, inclua uma lista de padrões de nomes de usuário. Separe os padrões com espaços. Se você especificar **Login**, será permitido apenas para nomes de usuários que
corresponderem a um dos padrões. É possível usar `"*" e "?"` como curingas nos padrões. Apenas nomes de usuário
são válidos; um ID do usuário numérico não é reconhecido. Por padrão,
**Login** é permitido para todos os usuários. Se o padrão assume o formato USER@HOST, então USER e HOST são verificados
separadamente, restringindo logins para usuários específicos de hosts específicos.

### DenyGroups 

Após essa palavra-chave, inclua uma lista de padrões de nome de grupo. Separe os padrões com espaços. Se
você especificar **Login**, será desaprovado para usuários cujo grupo primário ou
grupo complementar corresponde a um dos padrões. É possível usar `"*" e "?"` como curingas nos padrões. Apenas nomes de grupo são válidos; um ID do grupo numérico não é reconhecido. Por
padrão, **Login** é permitido para todos os grupos.

### DenyUsers 

Após essa palavra-chave, inclua uma lista de padrões de nomes de usuário. Separe os padrões com espaços. Se você especificar **Login**, será permitido para nomes de usuários que corresponderem a
um dos padrões. É possível usar`"*" e "?"` como curingas nos padrões. Apenas nomes de usuário
são válidos; um ID do usuário numérico não é reconhecido. Por padrão, **Login** é permitido
para todos os usuários.  Se o padrão assume o formato USER@HOST, então USER e HOST são verificados
separadamente, restringindo logins para usuários específicos de hosts específicos.

## Exemplo

No exemplo a seguir, apenas dois usuários específicos, `admin` e
`user1`, são permitidos para efetuar login no servidor.
**Nota:** é possível utilizar um método semelhante para negar grupos usando as palavras-chave
`DenyGroups` e `DenyUsers`.
```
AllowUsers admin user1
```

Para preparar para expansão futura de usuários, é possível criar um grupo no servidor que possa efetuar
login no servidor. É possível incluir usuários individuais conforme necessário (substitua
*`username`* pelo usuário real):

1. No shell, inclua um grupo de usuários, como sshusers:
```
groupadd –r sshusers
```

2. No shell, inclua usuários no grupo:
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. No arquivo sshd_config, dê acesso ao grupo sshusers:
```
AllowGroups sshusers
```

4. Verifique se sshd lê a nova configuração sem quebra:
```
/usr/sbin/sshd –t
```

```
echo $?
```

  Se você recebe `0` após o comando `echo $?` , a nova
configuração está correta.

  Também é possível obter mensagens de erro semelhantes aos exemplos a seguir:
```
sshd_config: line 112: Bad configuration option: allowuser
```

```
sshd_config: terminating, 1 bad configuration options
```

5. Depois de corrigir todos os erros e ter uma configuração correta, reinicie o sshd. A seguir está um comando de exemplo em um sistema compatível com sysv: /etc/init.d/sshd restart

Certifique-se de que você cria uma nova sessão SSH sem desconectar a sessão existente. Verifique se é
possível executar quaisquer ações com os usuários que você incluiu.
