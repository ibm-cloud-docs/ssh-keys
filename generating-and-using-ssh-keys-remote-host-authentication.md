---

copyright:
  years: 2014, 2019
lastupdated: "2019-05-06"

keywords: SSH keys, remote host authentication SSH keys, public-key cryptography

subcollection: ssh-keys

---

{:note: .note}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Generating and using SSH keys for remote host authentication
{: #generating-and-using-ssh-keys-for-remote-host-authentication}

SSH keys are a way to identify yourself to an SSH server that uses public-key cryptography and challenge-response authentication. An immediate advantage of this method over traditional password authentication is that you can be authenticated by the server without sending your password over the network. You can also use it with automation because it allows for unattended server communication.

## Generating SSH keys on Linux

To generate an SSH key on your Linux server run the command `ssh-keygen`. The command can take flags if you would like to customize the type of key that is generated as well as the signing algorithms used to generate the key. This example generates a standard 2048-bit RSA key without a passphrase. The command prompts you for the location to store the key (default is $HOME/.ssh/) as well as a passphrase to secure the SSH key.

    root@bck2:/etc# ssh-keygen
    Generating public/private rsa key pair.
    Enter file in which to save the key (/root/.ssh/id_rsa):
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in /root/.ssh/id_rsa.
    Your public key has been saved in /root/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx root@bck2.example.com
    The key's randomart image is:
    +---[RSA 2048]----+
    |.  oo*%=+o..     |
    |.++.oX+=. .      |
    |..+ooo=. .       |
    |   E.+. .o.      |
    |    +   S..+     |
    |     . +. =      |
    |      o  = o     |
    |      .o+ +      |
    |       +o.       |
    +----[SHA256]-----+

## Copying the public key to remote-hosts

To authenticate with a remote-host using your public SSH key you will use the `ssh-copy-id` command. Use the `-i` flag to specify the public key to copy to the remote-host.

    root@bck2: # ssh-copy-id -i /root/.ssh/id_rsa.pub root@10.176.18.15
    /usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/root/.ssh/id_rsa.pub"
    The authenticity of host '10.176.18.15 (10.176.18.15)' can't be established.
    ECDSA key fingerprint is SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.

    Are you sure you want to continue connecting (yes/no)? yes
    /usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
    /usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
    root@10.176.18.15's password:

    Number of key(s) added: 1

    Now try logging into the machine, with:   "ssh 'root@10.176.18.15'"
    and check to make sure that only the key(s) you wanted were added.

The ssh-copy-id command appends the keys to the remote-host’s .ssh/authorized_key file.
{:note}

## Testing that the key was copied correctly

To test that the public key was properly copied to the remote host simply ssh to the remote host.

    root@bck2:/etc# ssh root@10.176.18.15
    Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-53-generic x86_64)

    * Documentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/advantage

      Get cloud support with Ubuntu Advantage Cloud Guest:
        http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Fri Feb 10 16:51:51 2017 from 169.46.3.91
    root@bck1:~#

As you can see, there is not a prompt for the password when ssh-ing in to the remote host.

## SSH Keys with a passphrase

Providing a passphrase for your SSH key provides an additional layer of security, but it can also cause issues when you are trying to run automated scripts that require using the protected key.

The ssh-agent can manage your keys for you. You enter the passphrase once. The ssh-agent keeps your key in its memory and pulls it up when needed. To have ssh-agent manage your keys issue the following command:

    eval $(ssh-agent)

After the program starts using the ssh-add command to add your public key to the agent, the ssh-add utility searches for default keynames, of which id_rsa is one, and adds them to the ssh-agent. After you type your password, the "unlocked" key is stored with ssh-agent and can be used to authenticate against other servers.

    root@bck1:~# ssh-add
    Enter passphrase for /root/.ssh/id_rsa:
    Identity added: /root/.ssh/id_rsa (/root/.ssh/id_rsa)
    root@bck1:~#

Each time you open a new terminal session you will be prompted for the keys passphrase. Consider running the following commands to append your `.bash_profile` file so that ssh-agent starts with every bash session and your key is added.

    echo ‘eval $(ssh-agent)’ >> ~/.bash_profile
    echo ‘ssh-add’ >> ~/.bash_profile
