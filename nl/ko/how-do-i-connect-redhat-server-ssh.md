---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: RedHat server, main IP address of your server, default options

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSH를 사용하여 RedHat 서버에 연결
{: #connecting-to-a-redhat-server-with-ssh}

이 프로시저를 완료하려면 홈 컴퓨터에 PuTTY와 같은 SSH 클라이언트가 필요합니다. PuTTY는 널리 배포된 무료 SSH 클라이언트입니다.
대부분의 경우 처음에 PuTTY에서 기본 옵션을 사용하여 RedHat 서버에 연결할 수 있습니다.

1. PuTTY를 연 다음 `'호스트 이름(또는 IP 주소)'` 필드에 서버의 기본 IP 주소를 입력하고 열기를 클릭하십시오.

  SSH의 기본 포트는 22이지만 첫 번째 연결에 성공한 후 서버에서 변경할 수 있습니다.
  {:note} 
  
2. RedHat 서버가 사용자 이름 및 비밀번호를 묻는 프롬프트를 표시합니다. 서버의 루트 사용자/비밀번호 정보를 입력하십시오.
3. IP 주소 및 포트를 입력하여 세션에 연결 세부사항(IP 주소 및 포트)을 저장하십시오. "My Server"와 같은 해당 연결 특성의 제목을 작성하고 저장을 클릭하십시오.
  서버에 연결할 때 저장된 세션만 강조표시하고 열기를 클릭해야 합니다.

공용 네트워크를 사용하여 서버에 연결할 수 있습니다.
또한 사설 네트워크를 사용하여 연결할 수도 있습니다. VPN 연결에 대한 {{site.data.keyword.cloud}} 콘솔의 지시사항에 따라 SSH를 사용하여 사설 IP 주소에 연결하십시오.
