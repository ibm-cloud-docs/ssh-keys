---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Sobre as chaves SSH 

As chaves SSH são usadas pelos servidores SSH para identificar um usuário ou dispositivo por meio de
criptografia de chave pública. As chaves SSH são formadas por uma combinação alfanumérica e são exclusivas
para o dispositivo ao qual elas são designadas. A qualquer momento, os usuários autorizados podem incluir,
editar ou excluir chaves SSH usando o {{site.data.keyword.slportal_full}}.

As chaves SSH permitem acesso a um dispositivo sem usar uma senha de clientes correspondentes para cada
chave pública que é implementada no dispositivo. Ao incluir uma chave SSH em um dispositivo, que pode ser
feito durante o fornecimento ou por meio de um [Recarregamento de
OS](../software/vsi_reload_os.html), o dispositivo que foi fornecido com a chave SSH acessa o dispositivo para a chave correspondente
sem o uso de uma senha.
