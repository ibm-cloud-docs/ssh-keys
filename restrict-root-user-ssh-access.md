---

copyright:
  years: 2014, 2023
lastupdated: "2023-04-27"

keywords: root user, wheel group, SSH access Every Linux system

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Restricting the root user from SSH access
{: #restricting-the-root-user-from-ssh-access}

Every Linux system on the {{site.data.keyword.cloud}} network has a root user with administrative permissions. Within Linux, you can create wheel groups, which give users similar permissions to that of the root user through "sudo" without requiring the use of root user credentials. After you create a wheel group with sudo permissions of root, you can restrict the users in that group from SSH access. By restricting users this way, you protect the device from security vulnerabilities that pertain to network accessibility. Users that are part of the wheel group can still perform administrative functions on the device at any time.
{: shortdesc}

Follow these steps to restrict the root user from SSH access.

1. Open the 'etc/group' file and see whether it contains a line that defines a wheel group:

   ```
   wheel:x:10:root
   ```
   {: pre}

   If this line is not in the file, add it.

2. Add at least one user to the wheel group line:

   ```
   wheel:x:10:root, user1
   ```
   {: pre}

   Users that are added to the wheel group have identical permissions to the root user, but they use their unique username when they access the system.

3. Run the `:wq` command to save changes and exit the file.
4. Open the ```/etc/ssh/sshd_config``` and change the `PermitRootLogin yes` line to read `PermitRootLogin no`.
5. Run the `:wq` command to save changes and exit the file.
6. Type `visudo` at the **Command line** to generate command permissions.
7. Remove the **hash (#)** from the following line to uncomment the line:

   ```
   # %wheel ALL=(ALL) ALL
   ```
   {: pre}

   Uncommenting this line gives all users that are in the wheel group permission to run all commands.
   {:note}

8. Run the `:wq` command to save changes and exit the file.
9. Run the following command at the command line:

    ```
    vi /etc/pam.d/su
    ```
    {: pre}

10. Remove the **hash (#)** from the following line to uncomment the line:

    ```
    #auth required pam_wheel.so use_uid
    ```
    {: pre}

    Uncommenting this line requires users to be part of the wheel group to have permission to run all commands.
    {:note}

11. Run the `:wq` command to save changes and exit the file.
12. Run the following command to save all changes and restart SSH:

    ```
    # etc/init.d/ssh restart
    ```
    {: pre}

## Next steps
{: #next-steps-restricting-ssh-access}

After you restrict the root user from SSH access, the root user cannot log in to SSH. If a user currently can access the server through SSH under the root user, the connection will fail after the restart of SSH in the previous procedure. All future attempts to connect to SSH through the root user fail. To reverse these changes, repeat the steps and change `PermitRootLogin` no back to `PermitRootLogin` yes.
