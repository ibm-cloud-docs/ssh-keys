---

copyright: 2014, 2023
lastupdated: "2023-04-27"

keywords: list of group name patterns, SSH access, error messages, grant ssh access, ssh user access

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Granting SSH access to a user
{: #granting-ssh-access-to-a-user}

Use the following steps to grant SSH access to one or more users. These steps demonstrate how to configure this file.

1. Locate the following OpenSSH file:

   ```
   /etc/ssh/sshd_config
   ```
   {: screen}

2. Make a backup of this file so you can revert if necessary.

   ```
   cp /etc/ssh/sshd_config{,.'date +%s'}
   ```
   {: pre}

3. Edit the file by using the OpenSSH keywords.

## OpenSSH keywords
{: #openssh-keywords}

See the following information about OpenSSH keywords.

### AllowGroups
{: #allowgroups}

After this keyword, include a list of group name patterns. Separate the patterns with spaces. If you specify **Login**, it is allowed only for users whose primary group or supplementary group list matches one of the patterns. You can use `"*" and "?"` as wildcards in the patterns. Only group names are valid; a numerical group ID is not recognized. By default, **Login** is allowed for all groups.

### AllowUsers
{: #allowusers}

After this keyword, include a list of username patterns. Separate the patterns with spaces. If you specify **Login**, it is allowed only for usernames that match one of the patterns. You can use `"*" and "?"` as wildcards in the patterns. Only usernames are valid; a numerical user ID is not recognized. By default, **Login** is allowed for all users. If the pattern takes the form USER@HOST, then USER and HOST are separately checked, restricting logins to particular users from particular hosts.

### DenyGroups
{: #denygroups}

After this keyword, include a list of group name patterns. Separate the patterns with spaces. If you specify **Login**, it is disallowed for users whose primary group or supplementary group list matches one of the patterns. You can use `"*" and "?"` can be used as wildcards in the patterns. Only group names are valid; a numerical group ID is not recognized. By default, **Login** is allowed for all groups.

### DenyUsers
{: #denyusers}

After this keyword, include a list of username patterns. Separate the patterns with spaces. If you specify **Login**, it is disallowed for usernames that match one of the patterns. You can use`"*" and "?"` as wildcards in the patterns. Only usernames are valid; a numerical user ID is not recognized. By default, **Login** is allowed for all users. If the pattern takes the form USER@HOST, then USER and HOST are separately checked, restricting logins to particular users from particular hosts.

## Example
{: #example}

In the following example, only two specific users, `admin` and `user1` are allowed to log in to the server.

You can use a similar method to deny groups by using the keywords `DenyGroups` and `DenyUsers`.
{: tip}

   ```
   AllowUsers admin user1
   ```
   {: pre}

To prepare for future expansion of users, you can create a Group on the server that can log in to the server. You can add individual users as needed (replace *`username`* with the actual user):

1. In shell, add a user group, such as sshusers:

   ```sh
   groupadd –r sshusers
   ```
   {: pre}

2. In shell, add users to the group:

   ```sh
   usermod –a –G sshusers admin
   ```
   {: pre}

   ```sh
   usermod -a -G sshusers user1
   ```
   {: pre}

3. In the sshd_config file, give access to the sshusers group:

   ```sh
   AllowGroups sshusers
   ```
   {: pre}

4. Verify that sshd reads the new configuration without breaking:

   ```sh
   /usr/sbin/sshd –t
   ```
   {: pre}

   ```sh
   echo $?
   ```
   {: pre}

   If you get a `0` following the `echo $?` command, the new configuration is correct.

   You can also get error messages similar to the following examples:

   ```sshd_config: line 112: Bad configuration option: allowuser```

   ```sshd_config: terminating, 1 bad configuration options```

5. After you fix all errors and have a correct configuration, restart sshd. The following command is an example command in a sysv-compatible system:

   ```sh
   /etc/init.d/sshd restart
   ```
   {: pre}

Make sure that you create a new SSH session without disconnecting your existing session. Verify that you can perform any actions with the users that you added.
