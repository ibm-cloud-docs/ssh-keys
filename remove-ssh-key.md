---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH Key, Remove icon, obsolete SSH keys

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Removing an SSH key
{: #removing-an-ssh-key}

When an SSH key that is stored on the {{site.data.keyword.cloud}} console is obsolete or is no longer needed, you can remove the key. Remove obsolete SSH keys as soon as possible to ensure that there is enough space for additional, valid keys.
{:shortdesc}

## Before you begin
First, navigate to the device menu and ensure you have the correct account permissions to complete the tasks.

* Navigate to your console's device menu. For more information, see [Navigating to devices](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Ensure you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage Users** classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission) and [Managing device access](/docs/vsi?topic=virtual-servers-managing-device-access).

## Remove an SSH key

1. From the **Devices** menu, select **Manage > SSH Keys**.
2. Click the **Remove** icon next to the SSH key that you want to remove.
3. Click **Yes** to confirm. 

## Next steps

After you remove an SSH key, it is immediately removed from the list. The key can no longer be used when you provision a new device or when you perform an OS reload on an existing device. If the key is removed in error or needs to be added back to the {{site.data.keyword.cloud_notm}} console, see [Adding an SSH key](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key).
