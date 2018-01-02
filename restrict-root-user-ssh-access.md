---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-11"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restricting the root user from SSH access

Every Linux system on the {{site.data.keyword.cloud}} network has a root user with administrative permissions. Within Linux, you can create wheel groups, which give users similar permissions to that of the root user through "sudo" without requiring the use of root user credentials. After you create a wheel group with sudo permissions of root, you can restrict the users in that group from SSH access. By restricting users this way, you protect the device from security vulnerabilities that pertain to network accessibility. Users that are part of the wheel group can still perform administrative functions on the device at any time. 
{:shortdesc}

Follow these steps to restrict the root user from SSH access.

1. Open the 'etc/group' file and see whether it contains a line that defines a wheel group:

    ```wheel:x:10:root```
  
    If this line is not in the file, create it.

2. Add at least one user to the wheel group line:

    ```wheel:x:10:root, user1```
    
    Users added to the wheel group will have identical permissions to the root user, but they will use their unique user name when they access the system.
3. Run the `:wq` command to save changes and exit the file.
4. Open the ```/etc/ssh/sshd_config```.
5. Change the `PermitRootLogin yes` line to read `PermitRootLogin no`.
6. Run the `:wq` command to save changes and exit the file.
7. Type `visudo` at the **Command Line** to generate command permissions.
8. Remove the **hash (#)** from the following line to uncomment the line:

    ```# %wheel ALL=(ALL) ALL```
  
    **Note:** Uncommenting this line allows users in the wheel group to run all commands.
    
9. Run the `:wq` command to save changes and exit the file.
10. Run the following command at the command line:

    ```vi /etc/pam.d/su```
  
11. Remove the **hash (#)** from the following line to uncomment the line:

    ```#auth required pam_wheel.so use_uid```

    **Note:** Uncommenting this line requires users to be part of the wheel group to have permission to run all commands.
12. Run the `:wq` command to save changes and exit the file.
13. Run the following command to save all changes and restart SSH:

    ```# etc/init.d/ssh restart```

## Next Steps

After you restrict the root user from SSH access, the root user cannot log into SSH. If a user currently can access the server through SSH under the root user, the connection will fail after the restart of SSH in the previous procedure. All future attempts to connect to SSH through the root user will fail. To reverse these changes, repeat the steps and change `PermitRootLogin` no back to `PermitRootLogin` yes.
