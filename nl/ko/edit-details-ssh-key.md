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

# SSH 키의 세부사항 편집
{: #editing-details-for-an-ssh-key}

{{site.data.keyword.cloud}} 콘솔에서 [SSH 키를 추가](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)한 후 키 세부사항을 편집할 수 있습니다. 키의 **레이블**(SSH 키를 쉽게 식별하는 데 사용되는 단축 이름) 및 **참고**를 편집할 수 있습니다.
{:shortdesc}

## 시작하기 전에
먼저 디바이스 메뉴로 이동하여 태스크를 완료할 수 있는 올바른 계정 권한이 있는지 확인하십시오. 

* 콘솔의 디바이스 메뉴로 이동하십시오. 자세한 정보는 [디바이스로 이동](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)을 참조하십시오.
* 필요한 계정 권한 및 디바이스 액세스 권한이 있는지 확인하십시오. 계정 소유자 또는 **사용자 관리** 클래식 인프라 권한이 있는 사용자만 권한을 조정할 수 있습니다. 

권한에 대한 자세한 정보는 [클래식 인프라 권한](/docs/iam?topic=iam-infrapermission#infrapermission) 및 [디바이스 액세스 관리](/docs/vsi?topic=virtual-servers-managing-device-access)를 참조하십시오.

## SSH 키 세부사항 편집

키 자체를 편집해야 하는 경우 키를 제거하고 {{site.data.keyword.cloud_notm}} 콘솔에 올바른 키를 추가하십시오. SSH 키의 세부사항과 함께 나열된 지문은 키가 아닙니다. 키 검색에 사용되는 단축 바이트 시퀀스입니다. 어쨌든 지문은 실제 SSH 키를 나타내지 않습니다. 
{:note}

다음 단계를 완료하여 SSH 키 세부사항을 편집하십시오.

1. **디바이스** 메뉴에서 **관리 > SSH 키**를 선택하십시오. 
2. **레이블** 필드 또는 **참고** 필드의 아무 곳이나 클릭하여 편집할 필드를 여십시오.
3. 해당 필드에 업데이트된 텍스트를 입력하십시오.
4. 화면의 아무 곳이나 클릭하여 필드를 닫아 추가 편집하십시오.


## 다음 단계

편집된 SSH 키 세부사항은 SSH 키 목록에서 바로 업데이트됩니다.
