---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restricting SSH access on a public network

SSH accessibility provides users with the ability to securely access a device though an internet connection. SSH is available on {{site.data.keyword.cloud}} devices on both the public and private network. However, you should restrict SSH accessibility over the public network unless it is necessary for a unique business need. By restricting SSH access on the public network, users can still access a device over the private network, but risk from unknown users accessing the device on the public network is mitigated. If SSH accessibility over the public network is necessary, it is recommended to transfer SSH to a custom port number for an added layer of security. 
{:shortdesc}

Follow these steps to restrict SSH access on the public network.
1. Access the **Private Network** over [VPN ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.softlayer.com/vpn-access){: new_window}.
2. Log in to the Bare Metal Server **Private IP Address** through SSH.
3. Run the following command to open the `sshd_config` file for edits:
  > `vi /etc/ssh/sshd_config`
4. Remove the **hash (#)** from one `ListenAddress` line to uncomment the line.
5. Enter the **Private IP Address** for the Bare Metal Server in the uncommented `ListenAddress` line.
6. Run the `:wq` command to save the changes and exit the file.
7. Restart the sshd service
  > `service sshd restart`
8. Test the updates to SSH accessibility by attempting to access SSH over the Bare Metal Server's public IP address.<br><br><table border="1"><tr><th>If a connection...</th><th>Then...</th></tr><tr><td>Cannot be made</td><td>Changes made to SSH accessibility were successful. No further action is required.</td></tr><tr><td>Can be made</td><td>Changes made to SSH accessibility were unsuccessful. Repeat the steps above to retry SSH restriction. If issues persist, please [contact Support](https://control.softlayer.com/).</td></tr></table>

## Next Steps

After successfully restricting SSH access, users will be unable to access the device through SSH when they are not connecting through the private network. This action may be reversed at any time by adding the hash (#) back to the uncommented line, which returns the line to comments.
