# ansible-cybersec

This repository was created to provide ansible configurations files to automatically bootstrap and deploy Debian-based systems with penetration testing/CTF/cyber-security capabilities. On the opposite of Kali Linux, or Parrot OS Security, the goal of these updated systems is to be stable, come with a minimal yet sufficient number of tools, and easy to use.

This could be a good way to get into Ansible and Hacking at the same time.

# Recommendations

## SSH Keys

If is it not the case already, you should use a private/public key pair in order to make SSH connections to your infrastructure. To use Ansible with an SSH keypair, you should use a dedicated key for this purpose.

Recommended options for generating keys :

<code> ssh-keygen -t rsa -b 4096 -o -a 100 -C "Your personal keypair description" </code>

or 

<code> ssh-keygen -t ed25519 -a 100 -C "Your personal keypair description" </code>

*It is recommended to change the default path proposed by ssh-keygen in order to improve security*

After which you will need to export the public key of your newly created keypair to the specific host(s) on which you want to deploy with Ansible

<code> ssh-copy-id -i /path/to/your/keypair.pub IP.of.the.target </code>

## Bootstraping the OS


## Install common desktop softwares


## Configure common desktop softwares


## Install pentesting dependencies


## Install pentesting softwares
