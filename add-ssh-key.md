---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Adding an SSH key

You can add SSH keys to your account if you are an authorized user. Each account can have up to 100 SSH keys at any time. Within the {{site.data.keyword.slportal_full}}, SSH keys are most often used in the [OS reload process](../software/vsi_reload_os.html){:new_window} and can also be used when you provision a new device. 

**Note:** [Generate the public SSH key ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://help.github.com/articles/generating-ssh-keys){: new_window} with the device for which you are adding a key before adding an SSH key to your account. 

Follow these steps to add an SSH key to your account.
1. Access the **SSH Keys** screen. Refer to [Getting started with SSH Keys](index.html).
2. Click the **Add** tab at the top of the screen.
3. Click **Browse** to locate the public key file or enter it manually in the **Key Contents** text box.
4. Enter a **short name** for the SSH Key in the **Label** field.
5. Enter any applicable notes in the **Notes** field, if necessary.
6. Click **Add** to add the SSH key. Click **Cancel** to cancel the action.

## Next Steps

After you add the SSH key, it appears in the list of SSH keys. 
You can [edit the key details](edit-details-ssh-key.html) at any time. You can also [remove the SSH key](remove-ssh-key.html){:new_window} from the list. Remove obsolete SSH keys as soon as possible to ensure that space is available if you need to add more keys.