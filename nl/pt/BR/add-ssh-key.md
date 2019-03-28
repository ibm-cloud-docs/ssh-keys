---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Incluindo uma chave SSH
{: #adding-an-ssh-key}

É possível incluir chaves SSH na sua conta se você é um usuário autorizado. Cada conta pode ter até 100
chaves SSH a qualquer momento. No {{site.data.keyword.slportal_full}}, as chaves SSH são usadas com mais frequência no [Processo de recarregamento de OS](/docs/infrastructure/software?topic=software-reloading-the-os) e também podem ser usadas ao fornecer um novo dispositivo.

**Nota:** [gere a chave SSH pública ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://help.github.com/articles/generating-ssh-keys){: new_window} com o dispositivo para o qual você está incluindo uma chave antes de incluir uma chave SSH na sua conta.

Siga estas etapas para incluir uma chave SSH na sua conta.
1. Acesse a tela **Chaves SSH**. Consulte [Introdução às Chaves SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial).
2. Clique em **Incluir**.
3. Clique em **Procurar** para localizar o arquivo de chave pública ou insira-o manualmente na caixa de texto **Conteúdo de chave**.
4. Insira um **nome abreviado** para a Chave SSH no campo **Rótulo**.
5. Insira quaisquer notas aplicáveis no campo **Notas**, se necessário.
6. Clique em **Incluir** para incluir a chave SSH. Clique em **Cancelar** para cancelar a ação.

## Próximas Etapas

Depois de incluir a chave SSH, ela aparece na lista de chaves SSH.
É possível [editar os detalhes da chave](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key) a qualquer momento. Também é possível [remover a chave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key) da lista. Remova as chaves SSH obsoletas assim que possível para assegurar que espaço esteja disponível caso você precise incluir
mais chaves.
