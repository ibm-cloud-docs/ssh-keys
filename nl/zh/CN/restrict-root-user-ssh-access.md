---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 限制 root 用户进行 SSH 访问

{{site.data.keyword.cloud}} 网络上的每个 Linux 系统都有具有管理许可权的 root 用户。在 Linux 中，您可以创建 wheel 组，该组可通过“sudo”给予用户与 root 用户相似的权限，而无需使用 root 用户凭证。在创建了具有 sudo root 用户权限的 wheel 组之后，可以限制该组中的用户进行 SSH 访问。通过以这种方式限制用户，可以保护设备避免由于网络可访问而带来的安全漏洞。作为 wheel 组成员的用户仍可随时在设备上执行管理功能。
{:shortdesc}

按照下列步骤限制 root 用户进行 SSH 访问。

1. 打开“etc/group”文件，查看其中是否包含定义 wheel 组的一行：
```
wheel:x:10:root
```
  
    如果文件中没有此行，请创建此行。

2. 将至少一个用户添加到该 wheel 组行：
```
wheel:x:10:root, user1
```
    
    被添加到 wheel 组的用户都将具有与 root 用户相同的权限，但他们在访问系统时会使用他们唯一的用户名。
3. 运行 `:wq` 命令以保存更改并退出该文件。
4. 打开 `/etc/ssh/sshd_config`。
5. 将 `PermitRootLogin yes` 行的内容更改为 `PermitRootLogin no`。
6. 运行 `:wq` 命令以保存更改并退出该文件。
7. 在**命令行**中输入 `visudo` 以生成命令权限。
8. 从以下行中除去井号 **#** 以取消注释该行：
```
# %wheel ALL=(ALL) ALL
```
  
    **注：**取消注释此行可允许 wheel 组中的用户运行所有命令。
    
9. 运行 `:wq` 命令以保存更改并退出该文件。
10. 在命令行中运行下列命令：
```
vi /etc/pam.d/su
```
  
11. 从以下行中除去井号 **#** 以取消注释该行：
```
#auth required pam_wheel.so use_uid
```

    **注：**取消注释此行要求用户是 wheel 组的成员并有权运行所有命令。
12. 运行 `:wq` 命令以保存更改并退出该文件。
13. 运行以下命令以保存所有更改，然后重新启动 SSH：
```
# etc/init.d/ssh restart
```

## 后续步骤

在限制 root 用户进行 SSH 访问之后，root 用户将无法登录 SSH。如果用户当前可以在 root 用户下通过 SSH 访问服务器，那么在先前的过程中重新启动 SSH 后，连接会失败。未来尝试通过 root 用户连接 SSH 都会失败。要撤销这些更改，请重复上述步骤并将 `PermitRootLogin` no 更改回 `PermitRootLogin` yes。
