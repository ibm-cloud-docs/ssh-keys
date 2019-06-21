---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH 키 제거
{: #removing-an-ssh-key}

{{site.data.keyword.cloud}} 콘솔에 저장된 SSH 키가 더 이상 사용되지 않거나 필요하지 않은 경우 키를 제거할 수 있습니다. 사용하지 않는 SSH 키를 가능한 한 빨리 제거하여 올바른 추가 키를 위한 공간이 충분한지 확인하십시오.
{:shortdesc}

## 시작하기 전에
먼저 디바이스 메뉴로 이동하여 태스크를 완료할 수 있는 올바른 계정 권한이 있는지 확인하십시오. 

* 콘솔의 디바이스 메뉴로 이동하십시오. 자세한 정보는 [디바이스로 이동](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices)을 참조하십시오.
* 필요한 계정 권한 및 디바이스 액세스 권한이 있는지 확인하십시오. 계정 소유자 또는 **사용자 관리** 클래식 인프라 권한이 있는 사용자만 권한을 조정할 수 있습니다. 

권한에 대한 자세한 정보는 [클래식 인프라 권한](/docs/iam?topic=iam-infrapermission#infrapermission) 및 [디바이스 액세스 관리](/docs/vsi?topic=virtual-servers-managing-device-access)를 참조하십시오.

## SSH 키 제거

1. **디바이스** 메뉴에서 **관리 > SSH 키**를 선택하십시오.
2. 제거할 SSH 키 옆에 있는 **제거** 아이콘을 클릭하십시오.
3. 확인하려면 **예**를 클릭하십시오. 

## 다음 단계

SSH 키를 제거하면 목록에서 바로 제거됩니다. 새 디바이스를 프로비저닝하거나 기존 디바이스에서 OS 재로드를 수행하는 경우 키를 더 이상 사용할 수 없습니다. 오류에서 키를 제거하거나 키를 {{site.data.keyword.cloud_notm}} 콘솔에 다시 추가해야 하는 경우 [SSH 키 추가](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key)를 참조하십시오.
