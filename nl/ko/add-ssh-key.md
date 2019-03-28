---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH 키 추가
{: #adding-an-ssh-key}

권한 부여된 사용자의 경우 계정에 SSH 키를 추가할 수 있습니다. 각 계정은 언제든 최대 100개의 SSH 키를 가질 수 있습니다. {{site.data.keyword.slportal_full}} 내에서 SSH 키는 [OS 재로드 프로세스](/docs/infrastructure/software?topic=software-reloading-the-os)에 자주 사용되며 사용자가 새 디바이스를 프로비저닝하는 경우에도 사용될 수 있습니다.

**참고:** 계정에 SSH 키를 추가하기 전에 키를 추가하는 디바이스에서 [공개 SSH 키를 생성 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://help.github.com/articles/generating-ssh-keys){: new_window}하십시오.

다음 단계에 따라 계정에 SSH 키를 추가하십시오.
1. **SSH 키** 화면에 액세스하십시오. [SSH 키 시작하기](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial)를 참조하십시오.
2. **추가**를 클릭하십시오.
3. **찾아보기**를 클릭하여 공개 키 파일을 찾거나 **키 컨텐츠** 텍스트 상자에 수동으로 입력하십시오.
4. **레이블** 필드에 SSH 키의 **단축 이름**을 입력하십시오.
5. 필요한 경우 **참고** 필드에 해당 참고사항을 입력하십시오.
6. SSH 키를 추가하려면 **추가**를 클릭하십시오. 조치를 취소하려면 **취소**를 클릭하십시오.

## 다음 단계

SSH 키를 추가하면 이 키가 SSH 키 목록에 표시됩니다.
언제든 [키 세부사항을 편집](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key)할 수 있습니다. 또한 목록에서 [SSH 키를 제거](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key)할 수도 있습니다. 키를 추가해야 하는 경우 공간을 확보하기 위해 가능한 한 빨리 사용하지 않는 SSH 키를 제거하십시오.
