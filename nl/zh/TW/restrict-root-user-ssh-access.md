---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 限制 root 使用者的 SSH 存取
{: #restricting-the-root-user-from-ssh-access}

{{site.data.keyword.cloud}} 網路上的每個 Linux 系統都有具有管理許可權的 root 使用者。在 Linux 內，您可以建立 wheel 群組，它們透過 "sudo" 提供使用者與 root 使用者類似的許可權，而不需要使用 root 使用者認證。在您建立具有 root sudo 許可權的 wheel 群組之後，您可以限制該群組使用者的 SSH 存取。藉由以這種方式限制使用者，您可以保護裝置避免與網路可存取性相關的安全漏洞。隸屬於 wheel 群組的使用者仍可隨時在裝置上執行管理功能。
{:shortdesc}

請遵循下列步驟以限制 root 使用者的 SSH 存取。

1. 開啟 'etc/group' 檔案，查看它是否包含定義 wheel 群組的行：
```
wheel:x:10:root
```

    如果這行不在檔案中，請建立它。

2. 新增至少一個使用者至 wheel 群組行：
```
wheel:x:10:root, user1
```

    新增至 wheel 群組的使用者將具有與 root 使用者相同的許可權，但他們在存取系統時會使用他們的唯一使用者名稱。
3. 執行 `:wq` 指令，以儲存變更並結束檔案。
4. 開啟 `/etc/ssh/sshd_config`。
5. 將 `PermitRootLogin yes` 行變更為 `PermitRootLogin no`。
6. 執行 `:wq` 指令，以儲存變更並結束檔案。
7. 在**指令行**鍵入 `visudo`，以產生指令許可權。
8. 從下行移除**井字號 (#)**，以解除該行的註解。
```
# %wheel ALL=(ALL) ALL
```

   將此行解除註解可允許 wheel 群組中的使用者執行所有指令。
   {:note}

9. 執行 `:wq` 指令，以儲存變更並結束檔案。
10. 在指令行執行下列指令：
```
vi /etc/pam.d/su
```

11. 從下行移除**井字號 (#)**，以解除該行的註解。
```
#auth required pam_wheel.so use_uid
```

   將此行解除註解需要使用者隸屬於 wheel 群組，才能有執行所有指令的許可權。
   {:note}
   
12. 執行 `:wq` 指令，以儲存變更並結束檔案。
13. 執行下列指令以儲存所有變更，並重新啟動 SSH：
```
# etc/init.d/ssh restart
```

## 後續步驟

限制 root 使用者的 SSH 存取之後，root 使用者便無法登入 SSH。如果使用者目前可以用 root 使用者身分透過 SSH 存取伺服器，在先前程序中重新啟動 SSH 之後，連線將會失敗。未來所有透過 root 使用者連接 SSH 的嘗試都會失敗。若要回復這些變更，請重複步驟並將 `PermitRootLogin no` 改回 `PermitRootLogin yes`。
