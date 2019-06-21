---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: IP address, service sshd restart, private network

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 사설 네트워크에서만 청취하도록 SSH 구성
{: #configuring-ssh-to-listen-only-on-a-private-network}

백엔드 네트워크에서만 SSHd를 실행하여 서버의 보안을 강화할 수 있습니다. 따라서 SSH에 액세스할 때마다 VPN에 연결해야 합니다.

1. 다음 파일을 찾으십시오. 이 파일을 사용하여 `sshd`의 IP 주소를 정의하십시오.
```
# nano /etc/ssh/sshd_config
```

2. `ListenAddress 0.0.0.0`이 포함된 행을 찾으십시오. '#' 문자로 시작하는 경우 이 문자를 제거하십시오. IP 주소를 청취할 IP로 설정하십시오. {{site.data.keyword.cloud}} 콘솔에서 *하드웨어*를 선택하여 내부 IP 주소를 찾을 수 있습니다.
3. 변경 후 SSH 서비스를 다시 시작하십시오.
```
# service sshd restart
```

서비스를 다시 시작하면 현재 쉘 창의 연결이 끊깁니다. 현재 쉘 창을 종료하기 전에 새 SSH 포트를 통해 서버에 연결할 수 있는지 확인하십시오. 문제점이 있는 경우 SSHd 다시 시작에 실패하며, 대체 방법을 사용하여 서버에 연결해야 합니다.
