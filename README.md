# MelissaMiddleberg.com

## Prerequisites

  + *Virtualbox*
    + Choose the appropriate download for your operating system here:
      + `https://www.virtualbox.org/wiki/Downloads`

  + *Vagrant*
    + Choose the appropriate download for your operating system here:
      + `http://www.vagrantup.com/downloads.html`

## Installation

  + Open your terminal

#### Cloning Your Repository to Your Local Machine

  + execute `git clone git@github.com:melissamiddleberg/melissamiddleberg.com.git`
    + Note if you do not have your ssh key added to github execute the following:
      + `git clone https://github.com/melissamiddleberg/melissamiddleberg.com.git`
        + you will be prompted for your github username and password

#### Booting Up Your VM

*Note* - Virtualbox and Vagrant must be installed.

  + Once your repository has finished cloning, execute the following:
    + `vagrant up`
      + Your VM will be downloaded to your machine, and then it will be booted

#### Installing lamp on your VM

  + Execute `vagrant ssh` and you will now be in your VM.
    + *Note*: You must be in the directory with your Vagrantfile.
    + *Note*: Your VM must also be running via `vagrant up`

  + Execute `cd /vagrant`
  + Next execute `sudo chmod 777 scripts/debian-wheezy-lamp-install`
  + Run `sudo scripts/debian-wheezy-lamp-install`
    + *Note*: you will be prompted to enter in a password for your mysql install, use `root`
  + Verifying install:
    + Point your browser to `http://192.168.33.10/info.php`
      + You should see something with the PHP logo and `PHP Version 5.4.4-14+deb7u8` in the title

#### Installing vsftpd

  + Execute `sudo apt-get install vsftpd`

  + Now we need to edit the config filed to allow local user access, as well as make the folder writable

  + The config file is located in `/etc/vsftpd.conf`
    + Open it with your favorite text editor
    + Change `anonymous_enable=NO` to `anonymous_enable=YES`
    + Uncomment `local_enable=YES`
    + Uncomment `write_enable=YES`
