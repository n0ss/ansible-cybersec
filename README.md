# ansible-cybersec

This repository was created to provide ansible configurations files to automatically bootstrap and deploy Debian-based systems with penetration testing/CTF/cyber-security capabilities. On the opposite of Kali Linux, or Parrot OS Security, the goal of these updated systems is to be stable, come with a minimal yet sufficient number of tools, and easy to use.

This could be a good way to get into Ansible and Hacking at the same time.

# Recommendations (Optionnal)

## SSH Keys

You can use connect via SSH, and deploy with Ansible using only password protected connection. But this is not the right way to do it.

It is highly recommended that you use a private/public key pair in order to make SSH connections to your infrastructure. 

To use Ansible with an SSH keypair, you should use a dedicated key pair for this purpose. 

In this section, we're gonna create 2 key pairs, one for SSH logging, and one for Ansible.

### Dependencies

First, you'll to have an OpenSSH server running on your target, if not, install with :

<code> sudo apt install openssh-server -y </code>

### Generaring new key pair for SSH connections

Recommended options for generating keys :

<code> ssh-keygen -t rsa -b 4096 -o -a 100 -C "Your personal keypair description" </code>

or 

<code> ssh-keygen -t ed25519 -a 100 -C "Your personal keypair description" </code>

*It is recommended to change the default path proposed by ssh-keygen in order to improve security*

<code> Enter passphrase (empty for no passphrase): </code>

*When ssh-keygen asks you to enter a passphrase, it is highly recommended that you use one.*

***Example*** : *my+awesome+super+secret+passphrase*

### Exporting a public key to your target host

You will need to export the public key of your keypair to the specific host(s) on which you want to connect

<code> ssh-copy-id -i /path/to/your/keypair.pub IP.of.the.host </code>

Type the password of the remote host when asked, then logging to the host to verify successful export :

<code> ssh IP.of.the.host </code>

<code> cat ~/.ssh/authorized_keys </code>

### Using personal key to clone Github repositories

You can also use your public key to clone github repositories.

***Account/Preferences/SSH & GPG keys/New SSH Key/Paste your public key***

This will allow you to connect in a secure manner to Github.

### Generating second key pair for Ansible

Recommended options for generating keys :

<code> ssh-keygen -t rsa -b 4096 -o -a 100 -C "Your personal keypair description" </code>

or 

<code> ssh-keygen -t ed25519 -a 100 -C "Your personal keypair description" </code>

### Exporting a public key to your target host

In order to deploy with Ansible using your SSH key pair, you will need to export the public key of your keypair to the specific host(s) on which you want to deploy

<code> ssh-copy-id -i /path/to/your/keypair.pub IP.of.the.host </code>

Type the password of the remote host when asked, then logging to the host to verify successful export :

<code> ssh IP.of.the.host </code>

<code> cat ~/.ssh/authorized_keys </code>

# Bootstraping the OS


# Install common desktop softwares


# Configure common desktop softwares


# Install pentesting dependencies


# Install pentesting softwares
