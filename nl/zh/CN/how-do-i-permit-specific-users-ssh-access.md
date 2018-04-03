---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 为用户授予 SSH 访问权 

按照下列步骤为一个或多个用户授予 SSH 访问权。这些步骤演示了如何配置此文件：

1. 找到以下 OpenSSH 文件：
```
/etc/ssh/sshd_config
```
  
2. 生成此文件的备份，这样就可以在需要时进行还原。例如：

```
cp /etc/ssh/sshd_config{,.'date +%s'}
```
  
3. 使用 OpenSSH 关键字来编辑文件。


## OpenSSH 关键字

### AllowGroups 

在此关键字之后，包含一个组名模式列表。模式之间以空格分隔。如果指定**登录**，那么仅允许主组或补充组列表与其中某个模式相匹配的用户登录。可以使用`“*”和“?”`作为模式中的通配符。只有组名有效；无法识别数字组标识。缺省情况下，允许所有组**登录**。

### AllowUsers 

在此关键字之后，包含一个用户名模式列表。模式之间以空格分隔。如果指定**登录**，那么仅允许用户名与其中某个模式相匹配的用户登录。可以使用`“*”和“?”`作为模式中的通配符。只有用户名有效；无法识别数字用户标识。缺省情况下，允许所有用户**登录**。如果模式的形式是 USER@HOST，那么将分别检查 USER 和 HOST，限制仅允许来自特定主机的特定用户登录。

### DenyGroups 

在此关键字之后，包含一个组名模式列表。模式之间以空格分隔。如果指定**登录**，那么不允许主组或补充组列表与其中某个模式相匹配的用户登录。可以使用`“*”和“?”`作为模式中的通配符。只有组名有效；无法识别数字组标识。缺省情况下，允许所有组**登录**。

### DenyUsers 

在此关键字之后，包含一个用户名模式列表。模式之间以空格分隔。如果指定**登录**，那么不允许用户名与其中某个模式相匹配的用户登录。可以使用`“*”和“?”`作为模式中的通配符。只有用户名有效；无法识别数字用户标识。缺省情况下，允许所有用户**登录**。如果模式的形式是 USER@HOST，那么将分别检查 USER 和 HOST，限制仅允许来自特定主机的特定用户登录。

## 示例

在以下示例中，只允许两个特定用户（`admin` 和 `user1`）登录服务器。
**注：**通过使用关键字 `DenyGroups` 和 `DenyUsers`，您可以使用类似的方法来拒绝组。
```
AllowUsers admin user1
```

要为未来的用户扩展做好准备，可以在服务器上创建一个可以登录服务器的组。您可以根据需要来添加单个用户（将 *`username`* 替换为实际用户）：

1. 在 shell 中，添加用户组，如 sshusers：
```
groupadd –r sshusers
```

2. 在 shell 中，将用户添加到组中：
```
usermod –a –G sshusers admin
```
```
usermod -a -G sshusers user1
```

3. 在 sshd_config 文件中，为 sshusers 组授予访问权：
```
AllowGroups sshusers
```

4. 验证 sshd 能否无中断地读取新配置：
```
/usr/sbin/sshd –t
```

```
echo $?
```

  如果在 `echo $?` 命令后收到 `0`，那么新配置正确。

  也可能会收到类似以下示例的错误消息：
```
sshd_config: line 112: Bad configuration option: allowuser
```

```
sshd_config: terminating, 1 bad configuration options
```

5. 在修正了所有错误并确认配置正确之后，重新启动 sshd。下面是 sysv-compatible 系统中的示例命令：
  /etc/init.d/sshd restart

确保创建新 SSH 会话时不会断开现有会话的连接。验证是否能以您添加的用户身份执行任意操作。
