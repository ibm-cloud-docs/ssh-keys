---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Granting SSH access to a user 

Follow these steps to grant SSH access to one or more users. These steps demonstrate how to configure this file:

1. Locate the following OpenSSH file:

  ```/etc/ssh/sshd_config```
  
2. Make a backup of this file so you can revert if necessary. For example:

  ```cp /etc/ssh/sshd_config{,.'date +%s'}```
  
3. Edit the file by using the OpenSSH keywords.


## OpenSSH keywords

### AllowGroups 

After this keyword, include a list of group name patterns. Separate the patterns with spaces. If you specify **Login**, it is allowed only for users whose primary group or supplementary group list matches one of the patterns. You can use `"*" and "?"` as wildcards in the patterns. Only group names are valid; a numerical group ID is not recognized. By default, **Login** is allowed for all groups.

### AllowUsers 

After this keyword, include a list of user name patterns. Separate the patterns with spaces. If you specify **Login**, it is allowed only for user names that match one of the patterns. You can use `"*" and "?"` as wildcards in the patterns. Only user names are valid; a numerical user ID is not recognized. By default, **Login** is allowed for all users. If the pattern takes the form USER@HOST, then USER and HOST are separately checked, restricting logins to particular users from particular hosts.

### DenyGroups 

After this keyword, include a list of group name patterns. Separate the patterns with spaces. If you specify **Login**, it is disallowed for users whose primary group or supplementary group list matches one of the patterns. You can use `"*" and "?"` can be used as wildcards in the patterns. Only group names are valid; a numerical group ID is not recognized. By default, **Login** is allowed for all groups.

### DenyUsers 

After this keyword, include a list of user name patterns. Separate the patterns with spaces. If you specify **Login**, it is disallowed for user names that match one of the patterns. You can use`"*" and "?"` as wildcards in the patterns. Only user names are valid; a numerical user ID is not recognized. By default, **Login** is allowed for all users.  If the pattern takes the form USER@HOST, then USER and HOST are separately checked, restricting logins to particular users from particular hosts.

## Example

In the following example, only two specific users, `admin` and `user1` are allowed to login to the server.
**Note:** You can use a similar method to deny groups by using the keywords `DenyGroups` and `DenyUsers`.

```AllowUsers admin user1```

To prepare for future expansion of users, you can create a Group on the server that can log into the server. You can add individual users as needed (replace *`username`* with the actual user):

1. In shell, add a user group, such as sshusers:

  ```groupadd –r sshusers```

2. In shell, add users to the group:

  ```usermod –a –G sshusers admin```

  ```usermod -a -G sshusers user1```

3. In the sshd_config file, give access to the sshusers group:

  ```AllowGroups sshusers```

4. Verify that sshd reads the new configuration without breaking:

  ```/usr/sbin/sshd –t```

  ```echo $?```

  If you get a `0` following the `echo $?` command, the new configuration is correct.

  You can also get error messages similar to the following examples:

  ```sshd_config: line 112: Bad configuration option: allowuser```

  ```sshd_config: terminating, 1 bad configuration options```

5. After you fix all errors and have a correct configuration, restart sshd. The following is an example command in a sysv-compatible system:
  /etc/init.d/sshd restart

Make sure that you create a new SSH session without disconnecting your existing session. Verify that you can perform any actions with the users that you added.