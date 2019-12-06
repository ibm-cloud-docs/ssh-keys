---

copyright:
  years: 2014, 2019
lastupdated: "2019-12-06"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Adding an SSH key
{: #adding-an-ssh-key}

You can add SSH keys to your account if you are an authorized user. Each account can have up to 100 SSH keys at any time. SSH keys are most often used in the [OS reload process](/docs/software?topic=software-reloading-the-os#reloading-the-os) and can also be used when you provision a new device.
{:shortdesc}

## Before you begin
{: #before-you-begin-adding-ssh-key}

First, generate your public SSH key, navigate to the device menu, and ensure you have the correct account permissions to complete the tasks.

* [Generate the public SSH key](/docs/vpc?topic=vpc-ssh-keys#locating-ssh-keys).
* Navigate to your console's device menu. For more information, see [Navigating to devices](/docs/infrastructure/ssh-keys?topic=virtual-servers-navigating-devices).
* Ensure you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage Users** classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission) and [Managing device access](/docs/vsi?topic=virtual-servers-managing-device-access).

## Adding an SSH key to your account
{: #adding-an-ssh-key-to-your-account}

Complete the following steps to add an SSH key to your account.

1. From the **Devices** menu, select **Manage > SSH Keys**.
2. Click **Add**.
3. Click **Browse** to locate the public key file or enter it manually in the **Key Contents** text box.
4. Enter a **short name** for the SSH Key in the **Label** field.
5. Enter any applicable notes in the **Notes** field, if necessary.
6. Click **Add** to add the SSH key. 

## Next steps
{: #next-steps-adding-ssh-key}

After you add the SSH key, it appears in the list of SSH keys. You can [edit the key details](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key#editing-details-for-an-ssh-key) at any time. You can also [remove the SSH key](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key#removing-an-ssh-key) from the list. Remove obsolete SSH keys as soon as possible to ensure that space is available if you need to add more keys.
