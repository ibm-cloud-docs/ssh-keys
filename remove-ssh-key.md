---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Removing an SSH Key

When an SSH key stored on the {{site.data.keyword.slportal_full}} is obsolete or is no longer needed, you can remove the key by using the SSH Keys screen. Remove obsolete SSH keys as soon as possible to ensure there is enough space for additional, valid keys.

1. Access the **SSH Keys** screen in the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){: new_window} using your unique credentials.
2. Click the **Remove** icon next to the SSH key that you want to remove.
3. Click **Yes** to confirm. Click **No** to cancel the action.

## Next Steps

After you remove an SSH key, it is immediately removed from the list. The key can no longer be used when you provision a new device or when you perform an OS reload on an existing device. If the key was removed in error or needs to be added back to the {{site.data.keyword.slportal}}, refer to [Adding an SSH key](add-ssh-key.html){:new_window}.
