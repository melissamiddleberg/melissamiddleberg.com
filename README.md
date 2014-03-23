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
    + Note you will be prompted to enter in a password for your mysql install, use `root`
