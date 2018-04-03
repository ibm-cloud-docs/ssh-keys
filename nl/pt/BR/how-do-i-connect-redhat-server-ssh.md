---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Conectando-se a um servidor RedHat com SSH

Para concluir este procedimento, é necessário um cliente SSH, como PuTTY, em seu computador pessoal. O PuTTY é um cliente SSH grátis amplamente distribuído.
Na maioria dos casos, é possível usar as opções padrão no PuTTY para conectar-se com sucesso ao seu servidor
RedHat pela primeira vez.

1. Abra o PuTTY e digite o endereço IP principal do servidor no campo `'Hostname (or IP
address)` e clique em Abrir.
  Nota: a porta padrão para SSH é 22, mas é possível mudá-la no servidor
após sua primeira conexão bem-sucedida.
2. O servidor RedHat solicita um nome de usuário e senha. Digite suas informações de usuário
raiz/passagem para o servidor.
3. Salve os detalhes da conexão (endereço IP e porta) em Sessões digitando o endereço IP e a porta. Crie um título para essas propriedades de conexão, como "Meu servidor", e clique em Salvar.
  Ao conectar-se ao seu servidor, é necessário destacar somente a sessão salva e clicar em Abrir.

É possível conectar-se ao seu servidor usando a rede pública.
Também é possível conectar-se usando a rede privada. Siga as instruções no
{{site.data.keyword.slportal_full}} sobre como conectar-se à VPN e, em seguida, use o SSH para
conectar-se ao seu endereço IP privado.
