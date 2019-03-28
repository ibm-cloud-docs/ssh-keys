---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: non-standard port, SSH, text editor

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以在非標準埠上執行
{: #configuring-ssh-to-run-on-a-non-standard-port}

請遵循下列步驟以強制 SSH 在非標準埠上執行：

1. 在文字編輯器中開啟 /etc/ssh/sshd_config。下列範例適用於 vi 編輯器。
```
# vi /etc/ssh/sshd_config
```

2. 瀏覽至下行：
```
# Port 22
```

3. 解除註解並編輯此行，以反映新的埠。
```
Port 2255
```
（這可以設為任何非標準埠）



4. 儲存並退出檔案，然後重新啟動 SSH。
```
# /etc/init.d/sshd restart
```

5. 如果您使用 SSH 以埠 22 連接至伺服器，您的連線將會捨棄，而您將需要使用新的埠重新連接。
