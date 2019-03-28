---

copyright:
  years: 2014, 2018
lastupdated: "2018-08-15"

keywords: SSH keys, public-key cryptography, SSH

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Sobre as chaves SSH
{: #about-ssh-keys}

As chaves SSH são usadas pelos servidores SSH para identificar um usuário ou dispositivo por meio de
criptografia de chave pública. As chaves SSH são formadas por uma combinação alfanumérica e são exclusivas
para o dispositivo ao qual elas são designadas. A qualquer momento, os usuários autorizados podem incluir,
editar ou excluir chaves SSH usando o {{site.data.keyword.slportal_full}}.

É possível solicitar chaves SSH durante o fornecimento ou através de uma [Recarga de S.O.](/docs/infrastructure/software?topic=software-reloading-the-os).


As chaves SSH permitem acesso a um dispositivo sem usar uma senha de clientes correspondentes para cada
chave pública que é implementada no dispositivo. Ao incluir uma chave SSH em um dispositivo, o dispositivo que foi fornecido com a chave SSH acessa o dispositivo da chave correspondente sem o uso de senha.
