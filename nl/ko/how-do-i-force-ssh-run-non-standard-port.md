---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 비표준 포트에서 실행되도록 SSH 구성
{: #configuring-ssh-to-run-on-a-non-standard-port}

다음 단계에 따라 SSH가 비표준 포트에서 실행되도록 하십시오.

1. 텍스트 편집기에서 /etc/ssh/sshd_config를 여십시오. 다음 예제는 vi 편집기에 대한 예제입니다.
```
# vi /etc/ssh/sshd_config
```

2. 다음 행으로 이동하십시오.
```
# Port 22
```

3. 주석을 해제하고 새 포트를 반영하도록 다음 행을 편집하십시오.
```
Port 2255
```
(이는 임의 비표준 포트로 설정할 수 있음)

4. 파일을 저장하고 종료한 후 SSH를 다시 시작하십시오.
```
# /etc/init.d/sshd restart
```

5. 포트 22에서 SSH를 사용하여 서버에 연결하는 경우 연결이 끊기고 새 포트를 사용하여 다시 연결해야 합니다.
