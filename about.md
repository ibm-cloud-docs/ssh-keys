---

copyright:
  years: 2014, 2023
lastupdated: "2018-08-15"

keywords: SSH keys, public-key cryptography, SSH

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# About SSH keys
{: #about-ssh-keys}

SSH keys are used by SSH servers to identify a user or device through public-key cryptography. SSH keys are made up of an alpha-numeric combination and are unique to the device to which they are assigned. At any time, authorized users can add, edit, or delete SSH keys by using the {{site.data.keyword.cloud}} console.
{: shortdesc}

You can request SSH keys during provisioning or through an [OS Reload](/docs/software?topic=software-reloading-the-os#reloading-the-os).

SSH keys allow access to a device without using a password from corresponding clients for each public key that is implemented on the device. By adding an SSH key to a device, the device that was provided with the SSH key accesses the device for the corresponding key without the use of a password.
