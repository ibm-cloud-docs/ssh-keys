---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 配置 SSH 以在非标准端口上运行

按照下列步骤强制 SSH 在非标准端口上运行：

1. 在文本编辑器中打开 /etc/ssh/sshd_config。以下示例是针对 vi 编辑器的。
```
# vi /etc/ssh/sshd_config
```
 
2. 浏览到以下行：
```
# Port 22
```
 
3. 取消注释并编辑此行以反映新端口。
```
Port 2255
``` 
（此值可设置为任何非标准端口）

4. 保存并退出文件，然后重新启动 SSH。
```
# /etc/init.d/sshd restart
```

5. 如果使用 SSH 在端口 22 上连接服务器，那么连接会中断，需要使用新端口重新连接。
