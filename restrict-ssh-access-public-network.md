---

copyright:
  years: 2020, 2024
lastupdated: "2024-07-08"

keywords: SSH access, public network SSH accessibility, private network

subcollection: ssh-keys

---

{{site.data.keyword.attribute-definition-list}}

# Restricting SSH access on a public network
{: #restricting-ssh-access-on-a-public-network}

SSH accessibility provides users with the ability to securely access a device though an internet connection. SSH is available on {{site.data.keyword.cloud}} devices on both the public and private network. However, it's a good idea to restrict SSH accessibility over the public network unless it is necessary for a unique business need. When you restrict SSH access on the public network, users can still access a device over the private network, but the risk from unknown users accessing the device on the public network is mitigated. If SSH accessibility over the public network is necessary, you can transfer SSH to a custom port number for an added layer of security.
{: shortdesc}

Use the following steps to restrict SSH access on the public network.

1. Access the **Private Network** over [VPN](https://www.ibm.com/products/vpn-access){: external}.
2. Log in to the Bare Metal Server **Private IP address** through SSH.
3. Run the following command to open the `sshd_config` file for edits.

   > `vi /etc/ssh/sshd_config`

4. Remove the **hash (#)** from one `ListenAddress` line to uncomment it.
5. Enter the **Private IP address** for the Bare Metal Server in the uncommented `ListenAddress` line.
6. Run the `:wq` command to save the changes and exit the file.
7. Restart the sshd service.

   > `service sshd restart`

8. Test the updates to SSH accessibility by attempting to access SSH over the Bare Metal Server's public IP address.
   | If a connection | Then... |
   |------|---------|
   | Can't be made... | Changes that were made to SSH accessibility were successful. No further action is required.|
   | Can be made... | Changes that were made to SSH accessibility were unsuccessful. Repeat the previous steps to retry the SSH restriction. If issues persist, [contact Support](/docs/get-support?topic=get-support-using-avatar). |

## Next steps
{: #next-steps-restricting-access-public-network}

After successfully restricting SSH access, users can't access the device through SSH if they don't connect through the private network. This action can be reversed at any time by adding the hash (#) back to the uncommented line, which returns the line to comments.
