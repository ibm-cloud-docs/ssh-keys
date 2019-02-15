---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQs: chaves SSH

## Em qual lugar posso encontrar a minha chave SSH?
{:faq}

As chaves SSH são específicas do dispositivo e estão localizadas dentro do dispositivo. Como cada sistema operacional é diferente, as etapas para localizar a chave SSH são específicas do OS. Para saber mais sobre como gerar uma chave SSH em um dispositivo, consulte o artigo do GitHub em [gerando chaves SSH ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window}.

## Quantas chaves SSH posso incluir em minha conta?
{:faq}

É possível associar até 100 chaves SSH a uma conta. Os usuários autorizados podem
[incluir 1 chave SSH](add-ssh-key.html) por vez usando o
{{site.data.keyword.slportal_full}}. Embora a maioria dos usuários não precisa de 100 chaves, é necessário remover quaisquer chaves que não forem necessárias para assegurar que o espaço esteja disponível para mais chaves válidas. Para obter mais informações, consulte [removendo chaves
SSH](remove-ssh-key.html){:new_window}.

## Eu não vejo minha chave SSH real listada, mas vejo uma impressão digital. O que é isso?
{:faq}

A impressão digital que é mostrada com os detalhes para uma chave SSH é uma sequência abreviada de bytes gerados pelo sistema. A impressão digital é menor do que a chave SSH em si e é usada para autenticar ou consultar a chave pública para o dispositivo associado.

## Se eu criar ou recarregar um dispositivo que usa um modelo de imagem, as chaves SSH serão transportadas?
{:faq}

Sim e não. Como cada dispositivo possui uma chave SSH exclusiva, a chave para o dispositivo recém-fornecido ou recarregado será diferente da imagem.  No entanto, as chaves SSH que estão associadas a uma Imagem Flex ou a um modelo de imagem padrão estão associadas ao dispositivo quando ele é fornecido ou recarregado. Também é possível incluir chaves durante o processo de configuração.

