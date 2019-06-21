---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Incluindo uma chave SSH
{: #adding-an-ssh-key}

É possível incluir chaves SSH na sua conta se você é um usuário autorizado. Cada conta pode ter até 100
chaves SSH a qualquer momento. As chaves SSH são mais frequentemente usadas no [processo de recarregamento do S.O.](/docs/software?topic=software-reloading-the-os#reloading-the-os) e também podem ser usadas quando você provisiona um novo dispositivo.
{:shortdesc}

## Antes de começar:
Primeiro, gere sua chave SSH pública, navegue para o menu do dispositivo e assegure-se de que tenha as permissões de conta corretas para concluir as tarefas.

* [Gere a chave SSH pública ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://help.github.com/articles/generating-ssh-keys){: new_window} para o seu dispositivo.
* Navegue para o menu de dispositivos do console. Para obter mais informações, consulte [Navegando para os dispositivos](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Assegure-se de que você tenha as permissões de conta e o acesso ao dispositivo necessários. Somente o proprietário da conta ou um usuário com a permissão de infraestrutura clássica **Gerenciar usuários** pode ajustar as permissões.

Para obter mais informações sobre as permissões, consulte [Permissões de infraestrutura clássica](/docs/iam?topic=iam-infrapermission#infrapermission) e [Gerenciando o acesso ao dispositivo](/docs/vsi?topic=virtual-servers-managing-device-access).

## Incluindo uma chave SSH em sua conta
Conclua as etapas a seguir para incluir uma chave SSH em sua conta.

1. No menu **Dispositivos**, selecione **Gerenciar > Chaves SSH**.
2. Clique em **Incluir**.
3. Clique em **Procurar** para localizar o arquivo de chave pública ou insira-o manualmente na caixa de texto **Conteúdo de chave**.
4. Insira um **nome abreviado** para a Chave SSH no campo **Rótulo**.
5. Insira quaisquer notas aplicáveis no campo **Notas**, se necessário.
6. Clique em **Incluir** para incluir a chave SSH. 

## Próximos passos

Depois de incluir a chave SSH, ela aparece na lista de chaves SSH. É possível [editar os detalhes da chave](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key) a qualquer momento. Também é possível [remover a chave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key) da lista. Remova as chaves SSH obsoletas assim que possível para assegurar que espaço esteja disponível caso você precise incluir
mais chaves.
