---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# About SSH keys 

SSH keys are used by SSH servers to identify a user or device through public-key cryptography. SSH keys are made up of an alpha-numeric combination and are unique to the device to which they are assigned. At any time, authorized users can add, edit, or delete SSH keys by using the {{site.data.keyword.slportal_full}}.

SSH keys allow access to a device without using a password from corresponding clients for each public key that is implemented on the device. By adding an SSH key to a device, which can be done during provisioning or through an [OS Reload](../software/vsi_reload_os.html), the device that was provided with the SSH key accesses the device for the corresponding key without the use of a password.
