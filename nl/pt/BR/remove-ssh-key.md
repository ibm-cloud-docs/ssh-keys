---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Removendo uma chave SSH
{: #removing-an-ssh-key}

Quando uma chave SSH armazenada no console do {{site.data.keyword.cloud}} estiver obsoleta ou não for mais necessária, será possível removê-la. Remova as chaves SSH obsoletas assim que possível para assegurar que haja espaço suficiente para chaves adicionais válidas.
{:shortdesc}

## Antes de começar:
Primeiro, navegue para o menu de dispositivos e assegure-se de ter as permissões de conta corretas para concluir as tarefas.

* Navegue para o menu de dispositivos do console. Para obter mais informações, consulte [Navegando para os dispositivos](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Assegure-se de que você tenha as permissões de conta e o acesso ao dispositivo necessários. Somente o proprietário da conta ou um usuário com a permissão de infraestrutura clássica **Gerenciar usuários** pode ajustar as permissões.

Para obter mais informações sobre as permissões, consulte [Permissões de infraestrutura clássica](/docs/iam?topic=iam-infrapermission#infrapermission) e [Gerenciando o acesso ao dispositivo](/docs/vsi?topic=virtual-servers-managing-device-access).

## Removendo uma chave SSH

1. No menu **Dispositivos**, selecione **Gerenciar > Chaves SSH**.
2. Clique no ícone **Remover** ao lado da chave SSH que você deseja remover.
3. Clique em **Sim** para confirmar. 

## Próximos passos

Depois de remover uma chave SSH, ela é imediatamente removida da lista. A chave não pode mais ser usada ao fornecer um novo dispositivo ou ao executar um recarregamento de S.O. em um dispositivo existente. Se a chave for removida com erro ou precisar ser incluída de volta no console do {{site.data.keyword.cloud_notm}}, consulte [Incluindo uma chave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key).
