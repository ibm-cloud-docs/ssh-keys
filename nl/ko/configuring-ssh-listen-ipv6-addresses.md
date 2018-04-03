---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IPv6 주소에서 청취하도록 SSH 구성

다음 프로시저에 따라 Linux 서버에서 SSH를 사용으로 설정하여 IPv6에서 청취하십시오.
1. /etc/ssh/sshd_config 파일을 찾으십시오.
2. `ListenAddress`가 포함된 행을 찾으십시오.
3. `#ListenAddress ::` 행을 주석 해제하십시오.
```
ListenAddress ::
```

이렇게 하면 디바이스의 모든 주소에 `sshd`가 바인드됩니다.
