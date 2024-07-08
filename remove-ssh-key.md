---

copyright:
  years: 2014, 2024
lastupdated: "2024-06-06"

keywords: remove ssh key, obsolete SSH keys

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Removing an SSH key
{: #removing-an-ssh-key}

When an SSH key that is stored on the {{site.data.keyword.cloud}} console is obsolete or is no longer needed, you can remove the key. Remove obsolete SSH keys as soon as possible to make sure that enough space is available for more valid keys.
{: shortdesc}

## Before you begin
{: #before-you-begin-removing-ssh-key}

* Go to the device menu and make sure that you have the correct account permissions to complete the tasks.

* Make sure that you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage users** Classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/virtual-servers?topic=virtual-servers-mngclassicinfra#how-classic-infra-permissions-work) and [Managing device access](/docs/virtual-servers?topic=virtual-servers-managing-device-access).

## Removing an SSH key
{: #removing-ssh-key}

1. From the **Devices** menu, select **Manage > SSH keys**.
2. Click the **Remove** icon next to the SSH key that you want to remove.
3. Click **Yes** to confirm.

## Next steps
{: #next-steps-removing-ssh-key}

After you remove an SSH key, it is immediately removed from the list. The key can no longer be used when you provision a new device or when you perform an OS reload on an existing device. If the key is removed in error or needs to be added back to the {{site.data.keyword.cloud_notm}} console, see [Adding an SSH key](/docs/ssh-keys?topic=ssh-keys-adding-an-ssh-key).
