---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restringindo o usuário raiz do acesso SSH

Cada sistema Linux na rede do {{site.data.keyword.cloud}} possui um usuário raiz com permissões
administrativas. No Linux, é possível criar grupos de roda, que dão aos usuários permissões semelhantes à do
usuário raiz por meio de "sudo" sem requerer o uso de credenciais do usuário raiz. Depois de criar um grupo de
roda com permissões sudo de raiz, é possível restringir os usuários nesse grupo do acesso SSH. Ao restringir
os usuários dessa maneira, você protege o dispositivo contra vulnerabilidades de segurança
referentes à acessibilidade de rede. Os usuários que fazem parte do grupo de roda ainda podem executar funções
administrativas no dispositivo a qualquer momento. 
{:shortdesc}

Siga estas etapas para restringir o usuário raiz do acesso SSH.

1. Abra o arquivo 'etc/group' e veja se ele contém uma linha que define um grupo de roda:
```
wheel:x:10:root
```
  
    Se essa linha não estiver no arquivo, crie-a.

2. Inclua pelo menos um usuário na linha de grupo de roda:
```
wheel:x:10:root, user1
```
    
    Os usuários incluídos no grupo de roda têm permissões idênticas às do usuário raiz, mas eles usam o seu nome de usuário exclusivo ao acessarem o sistema.
3. Execute o comando `:wq` para salvar as mudanças e sair do arquivo.
4. Abra o `/etc/ssh/sshd_config`.
5. Mude a linha `PermitRootLogin yes` para ler `PermitRootLogin
no`.
6. Execute o comando `:wq` para salvar as mudanças e sair do arquivo.
7. Digite `visudo` na **Linha de comandos** para gerar permissões
de comando.
8. Remova o **hash (#)** da linha a seguir para remover o comentário da linha:
```
# %wheel ALL=(ALL) ALL
```
  
    **Nota:** a remoção do comentário desta linha permite que os usuários no grupo
de roda executem todos os comandos.
    
9. Execute o comando `:wq` para salvar as mudanças e sair do arquivo.
10. Execute o seguinte comando na linha de comandos:
```
vi /etc/pam.d/su
```
  
11. Remova o **hash (#)** da linha a seguir para remover o comentário da linha:
```
#auth required pam_wheel.so use_uid
```

    **Nota:** a remoção do comentário desta linha requer que os usuários façam parte do
grupo de roda e que também tenham permissão para executar todos os comandos.
12. Execute o comando `:wq` para salvar as mudanças e sair do arquivo.
13. Execute o comando a seguir para salvar todas as mudanças e reiniciar o SSH:
```
# etc/init.d/ssh restart
```

## Próximas Etapas

Depois de restringir o usuário raiz do acesso SSH, o usuário raiz não poderá efetuar login no SSH. Se um
usuário atualmente puder acessar o servidor por meio de SSH sob o usuário root, a conexão falhará após a
reinicialização de SSH no procedimento anterior. Todas as tentativas futuras de conexão com o SSH por meio do usuário raiz falharão. Para reverter essas mudanças, repita as etapas e mude `PermitRootLogin no` novamente para `PermitRootLogin yes`.
