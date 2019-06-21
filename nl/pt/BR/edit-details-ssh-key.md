---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH key, key details, IBM Cloud infrastructure customer

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Editando detalhes para uma chave SSH
{: #editing-details-for-an-ssh-key}

Depois de [incluir uma chave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key) no console do {{site.data.keyword.cloud}}, é possível editar os detalhes da chave. É possível editar o
**Rótulo** (o nome abreviado que é usado para identificar facilmente a chave SSH) e as
**Notas** para a chave.
{:shortdesc}

## Antes de começar:
Primeiro, navegue para o menu de dispositivos e assegure-se de ter as permissões de conta corretas para concluir as tarefas.

* Navegue para o menu de dispositivos do console. Para obter mais informações, consulte [Navegando para os dispositivos](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Assegure-se de que você tenha as permissões de conta e o acesso ao dispositivo necessários. Somente o proprietário da conta ou um usuário com a permissão de infraestrutura clássica **Gerenciar usuários** pode ajustar as permissões.

Para obter mais informações sobre as permissões, consulte [Permissões de infraestrutura clássica](/docs/iam?topic=iam-infrapermission#infrapermission) e [Gerenciando o acesso ao dispositivo](/docs/vsi?topic=virtual-servers-managing-device-access).

## Editando os detalhes da chave SSH

Se você precisar editar a própria chave, remova-a e inclua a chave correta no console do {{site.data.keyword.cloud_notm}}. A impressão digital listada com os detalhes da chave SSH não é a chave em si. Ela é uma sequência curta de bytes usada na recuperação da chave. A impressão digital pode não representar a chave SSH real de modo algum. 
{:note}

Conclua as etapas a seguir para editar os detalhes da chave SSH.

1. No menu **Dispositivos**, selecione **Gerenciar > Chaves SSH**. 
2. Clique em qualquer lugar no campo **Rótulo** ou no campo **Notas** para abrir o campo para edições.
3. Digite o texto atualizado no campo correspondente.
4. Clique em qualquer lugar na tela para fechar o campo para mais edições.


## Próximos passos

Os detalhes da chave SSH que são editados são atualizados imediatamente na lista de chaves SSH.
