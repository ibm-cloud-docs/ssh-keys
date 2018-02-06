---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restringindo o acesso SSH em uma rede pública

A acessibilidade SSH fornece aos usuários a capacidade de acessar com segurança um dispositivo por meio de
uma conexão com a Internet. O SSH está disponível em dispositivos {{site.data.keyword.cloud}}
nas redes pública e privada. No entanto, é necessário restringir a acessibilidade SSH na rede pública, a menos
que ela seja necessária para uma necessidade de negócios exclusiva. Ao restringir o acesso SSH na rede
pública, os usuários ainda podem acessar um dispositivo pela rede privada, mas o risco de usuários
desconhecidos de acessarem o dispositivo na rede pública é reduzido. Se a acessibilidade SSH pela rede pública é
necessária, é recomendado transferir o SSH para um número de porta customizado para uma camada adicional de
segurança.
{:shortdesc}

Siga essas etapas para restringir o acesso do SSH na rede pública.
1. Acesse a **Rede privada** sobre
[VPN ![Ícone de link externo](../../icons/launch-glyph.svg "Íconede link externo")](http://www.softlayer.com/vpn-access){: new_window}.

2. Efetue login no Servidor Bare Metal usando o **Endereço IP privado** por
meio de SSH.
3. Execute o comando a seguir para abrir o arquivo `sshd_config` para edições:
  > `vi /etc/ssh/sshd_config`
4. Remova o **hash (#)** de uma linha `ListenAddress` para
remover o comentário da linha.
5. Insira o **Endereço IP privado** para o Servidor Bare Metal na linha
`ListenAddress` com comentário removido.
6. Execute o comando `:wq` para salvar as mudanças e sair do arquivo.
7. Reinicie o serviço sshd
  > `service sshd restart`
8. Teste as atualizações de acessibilidade SSH tentando acessar o SSH pelo endereço IP público
do Servidor Bare Metal.<br><br><table border="1"><tr><th>Se uma conexão...</th><th>Então...</th></tr><tr><td>
Não pode ser feita</td><td>As mudanças feitas na acessibilidade SSH foram bem-sucedidas. Nenhuma ação
adicional é necessária.</td></tr><tr><td>Pode ser feita</td><td>As mudanças feitas na acessibilidade de SSH
foram malsucedidas. Repita as etapas acima para tentar novamente a restrição SSH. Se os problemas persistirem,
[entre em contato com o Suporte](https://control.softlayer.com/).</td></tr></table>

## Próximas Etapas

Após a restrição com sucesso do acesso SSH, os usuários não poderão acessar o dispositivo por meio de
SSH quando eles não estiverem se conectando por meio da rede privada. Esta ação pode ser revertida a qualquer
momento incluindo o hash (#) de volta na linha com comentário removido, que retorna a linha aos comentários.
