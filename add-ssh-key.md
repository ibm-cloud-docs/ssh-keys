---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-06"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Adding an SSH key
{: #adding-an-ssh-key}

You can add SSH keys to your account if you are an authorized user. Each account can have up to 100 SSH keys at any time. Within the {{site.data.keyword.slportal_full}}, SSH keys are most often used in the [OS reload process](/docs/infrastructure/software?topic=software-reloading-the-os) and can also be used when you provision a new device.

[Generate the public SSH key ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://help.github.com/articles/generating-ssh-keys){: new_window} with the device for which you are adding a key before adding an SSH key to your account.
{:note}

Follow these steps to add an SSH key to your account.
1. Access the **SSH Keys** screen. Refer to [Getting started with SSH Keys](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial).
2. Click **Add**.
3. Click **Browse** to locate the public key file or enter it manually in the **Key Contents** text box.
4. Enter a **short name** for the SSH Key in the **Label** field.
5. Enter any applicable notes in the **Notes** field, if necessary.
6. Click **Add** to add the SSH key. Click **Cancel** to cancel the action.

## Next steps

After you add the SSH key, it appears in the list of SSH keys.
You can [edit the key details](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key) at any time. You can also [remove the SSH key](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key) from the list. Remove obsolete SSH keys as soon as possible to ensure that space is available if you need to add more keys.
