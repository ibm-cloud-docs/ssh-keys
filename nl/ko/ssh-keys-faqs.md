---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH keys, SSH key, device-specific

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQ: SSH 키
{: #faqs-ssh-keys}

## 내 SSH 키는 어디에서 찾을 수 있습니까?
{:faq}

SSH 키는 디바이스에 따라 다르며 디바이스 내에 있습니다. 각 운영 체제가 서로 다르므로 SSH 키를 찾는 단계도 OS에 따라 다릅니다. 디바이스에서 SSH 키를 생성하는 방법을 자세히 보려면 [SSH 키 생성 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window}의 GitHub 기사를 참조하십시오.

## 내 계정에 추가할 수 있는 SSH 키는 몇 개입니까?
{:faq}

계정에 최대 100개의 SSH 키를 연관시킬 수 있습니다. 권한 부여된 사용자는 {{site.data.keyword.cloud}} 콘솔을 사용하여 한 번에 [한 개의 SSH 키를 추가](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key)할 수 있습니다. 대부분의 사용자에게는 100개의 키가 필요하지 않으며 올바른 추가 키를 위한 공간을 확보하기 위해 필요 없는 키를 제거해야 합니다. 자세한 정보는 [SSH 키 제거](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key)를 참조하십시오.

## 내 실제 SSH 키가 나열되지는 않지만 지문이 표시됩니다. 왜 그렇습니까?
{:faq}

SSH 키에 대한 세부사항과 함께 표시되는 지문은 시스템에서 생성된 단축 바이트 시퀀스입니다. 지문은 SSH 키 자체보다 짧으며 연관된 디바이스의 공개 키를 인증하거나 검색하는 데 사용됩니다.

## 이미지 템플리트를 사용하는 디바이스를 작성하거나 다시 로드하는 경우 SSH 키가 전달됩니까?
{:faq}

예 및 아니오. 각 디바이스에는 고유 SSH 키가 있으므로 새로 프로비저닝된 디바이스 또는 다시 로드된 디바이스의 키가 이미지와 다릅니다.  하지만 Flex 이미지 또는 표준 이미지 템플리트와 연관된 SSH 키가 프로비저닝되거나 다시 로드된 경우 디바이스와 연관됩니다. 또한 설치 프로세스 중에 키를 추가할 수도 있습니다.
