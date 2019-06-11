---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-11"

keywords: SSH key, key details, IBM Cloud infrastructure customer

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Editing details for an SSH key
{: #editing-details-for-an-ssh-key}

After [adding an SSH key](/docs/infrastructure/ssh-keys?topic=ssh-keys-adding-an-ssh-key#adding-an-ssh-key) in the {{site.data.keyword.cloud}} console, you can edit the key details. You can edit the **Label** (the short name that is used to easily identify the SSH key) and the **Notes** for the key.
{:shortdesc}

## Before you begin
First, navigate to the device menu and ensure you have the correct account permissions to complete the tasks.

* Navigate to your console's device menu. For more information, see [Navigating to devices](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Ensure you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage Users** classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission) and [Managing device access](/docs/vsi?topic=virtual-servers-managing-device-access).

## Editing SSH key details

If you need to edit the key itself, remove the key and add the correct key to the {{site.data.keyword.cloud_notm}} console. The fingerprint that is listed with the details for the SSH key is not the key itself; it is a short sequence of bytes used in the retrieval of the key. The fingerprint might not represent the actual SSH key in any way. 
{:note}

Complete the following steps to edit SSH key details.

1. From the **Devices** menu, select **Manage > SSH Keys**. 
2. Click anywhere in the **Label** field or the **Notes** field to open the field for edits.
3. Type the updated text in the corresponding field.
4. Click anywhere on the screen to close the field to more edits.


## Next steps

SSH key details that are edited are updated immediately in the SSH keys list.
