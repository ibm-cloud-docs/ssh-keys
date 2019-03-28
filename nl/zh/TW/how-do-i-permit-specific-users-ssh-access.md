---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: list of group name patterns, SSH access, error messages

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 將 SSH 存取授與給使用者
{: #granting-ssh-access-to-a-user}

請遵循下列步驟，將 SSH 存取授與給一個以上的使用者。這些步驟示範如何配置這個檔案：

1. 找到下列 OpenSSH 檔案：
```
/etc/ssh/sshd_config
```

2. 備份這個檔案，以便您可以在必要時回復它。例如：
```
cp /etc/ssh/sshd_config{,.'date +%s'}
```

3. 使用 OpenSSH 關鍵字編輯檔案。


## OpenSSH 關鍵字

### AllowGroups

在這個關鍵字之後，包含群組名稱型樣的清單。請以空格來區隔型樣。如果您指定 **Login**，則只針對主要群組或增補群組清單符合其中一個型樣的使用者才允許它。您可以使用 `"*" 和 "?"` 作為型樣中的萬用字元。只有群組名稱有效，無法辨識數值群組 ID。依預設，所有群組都允許 **Login**。

### AllowUsers

在這個關鍵字之後，包含使用者名稱型樣的清單。請以空格來區隔型樣。如果您指定 **Login**，則只針對符合其中一個型樣的使用者名稱才允許它。您可以使用 `"*" 和 "?"` 作為型樣中的萬用字元。只有使用者名稱有效，無法辨識數值使用者 ID。依預設，所有使用者都允許 **Login**。如果型樣的格式為 USER@HOST，則 USER 和 HOST 會分開檢查，限制只有來自特定主機的特定使用者能登入。

### DenyGroups

在這個關鍵字之後，包含群組名稱型樣的清單。請以空格來區隔型樣。如果您指定 **Login**，則會針對主要群組或增補群組清單符合其中一個型樣的使用者禁止它。您可以使用 `"*" 和 "?"` 作為型樣中的萬用字元。只有群組名稱有效，無法辨識數值群組 ID。依預設，所有群組都允許 **Login**。

### DenyUsers

在這個關鍵字之後，包含使用者名稱型樣的清單。請以空格來區隔型樣。如果您指定 **Login**，則會針對符合其中一個型樣的使用者名稱禁止它。您可以使用 `"*" 和 "?"` 作為型樣中的萬用字元。只有使用者名稱有效，無法辨識數值使用者 ID。依預設，所有使用者都允許 **Login**。如果型樣的格式為 USER@HOST，則 USER 和 HOST 會分開檢查，限制只有來自特定主機的特定使用者能登入。

## 範例

在下列範例中，只有兩個特定的使用者 `admin` 和 `user1` 被允許登入伺服器。
**附註：**您可以使用類似方法，以關鍵字 `DenyGroups` 和 `DenyUsers` 來拒絕群組。
```
AllowUsers admin user1
```

若要準備未來的使用者擴張，您可以在可登入伺服器的伺服器上建立群組。您可以視需要新增個別使用者（將 *`username`* 取代為實際使用者）：

1. 在 Shell 中，新增使用者群組，例如 sshusers：
```
groupadd –r sshusers
```

2. 在 Shell 中，將使用者新增至群組：
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. 在 sshd_config 檔案中，提供存取給 sshusers 群組：
```
AllowGroups sshusers
```

4. 驗證 sshd 讀取新的配置而無岔斷：
```
/usr/sbin/sshd –t
```

```
echo $?
```

  如果您在 `echo $?` 指令之後得到 `0`，新的配置便正確。

  您也可能得得到類似下列範例的錯誤訊息：
```
sshd_config: line 112: Bad configuration option: allowuser
```

```
sshd_config: terminating, 1 bad configuration options
```

5. 修正所有錯誤並具有正確的配置之後，請重新啟動 sshd。以下是 sysv 相容系統中的範例指令：
  /etc/init.d/sshd restart

請確定您建立新的 SSH 階段作業時未中斷現有階段作業的連線。請驗證您可以使用您新增的使用者執行任何動作。
