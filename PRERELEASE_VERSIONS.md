# Early access to features and bug fixes between openMHA releases

openMHA typically has three to four public releases per year.
We recommend that hearing aid algorithm researchers use these
releases to conduct their own studies and refer to these in
publications.

Between these releases, we continuously develop new features and bug
fixes.  After internal review we make these features and bug fixes
available in installer packages for Ubuntu and in a development
version of the source code.

## 1. Ubuntu packages for development versions

You can install packages created from the development branch from a
separate apt repository.  Please be aware that

* Development versions of openMHA will replace existing openMHA releases on
  your computer.
* Development versions will be updated often.
* We will provide each development version only for a limited time (typically
  2 weeks).
* We recommend strongly against using development versions in scientific
  studies.  For the sake of reproducible research, please use released versions.

### 1.1 Installation of development versions on Ubuntu

In Ubuntu 24.04:

    wget -qO- http://apt.hoertech.de/openmha-packaging.pub | sudo tee /etc/apt/trusted.gpg.d/openmha-packaging.asc
    sudo apt-add-repository 'deb [arch=amd64] http://apt.hoertech.de noble universe'
    sudo apt-add-repository 'deb [arch=amd64] http://aptdev.hoertech.de noble universe'
    sudo apt install openmha openmha-examples

In Ubuntu 22.04:

    wget -qO- http://apt.hoertech.de/openmha-packaging.pub | sudo tee /etc/apt/trusted.gpg.d/openmha-packaging.asc
    sudo apt-add-repository 'deb [arch=amd64] http://apt.hoertech.de jammy universe'
    sudo apt-add-repository 'deb [arch=amd64] http://aptdev.hoertech.de jammy universe'
    sudo apt install openmha openmha-examples

In Ubuntu 20.04:

    wget -qO- http://apt.hoertech.de/openmha-packaging.pub | sudo apt-key add -
    sudo apt-add-repository 'deb [arch=amd64] http://apt.hoertech.de focal universe'
    sudo apt-add-repository 'deb [arch=amd64] http://aptdev.hoertech.de focal universe'
    sudo apt install openmha openmha-examples

On Computers with an ARM CPU running a variant of Debian, Ubuntu,
Raspberry Pi OS, Armbian, or similar:  The following instructions work for
both, 32 and 64 bit ARM systems.  A requirement for 32 bit ARM systems is that
the CPU needs to be at least ARMv7.

For ARM systems based on Debian 10 or Ubuntu 20.04:

    wget -qO- http://apt.hoertech.de/openmha-packaging.pub | sudo apt-key add -
    echo 'deb http://apt.hoertech.de bionic universe' | sudo tee /etc/apt/sources.list.d/openmha.list
    echo 'deb http://aptdev.hoertech.de bionic universe' | sudo tee /etc/apt/sources.list.d/openmhadev.list
    sudo apt update
    sudo apt install openmha openmha-examples

For ARM systems based on Debian 11 or Ubuntu 22.04 or later:

    wget -qO- http://apt.hoertech.de/openmha-packaging.pub | sudo tee /etc/apt/trusted.gpg.d/openmha-packaging.asc
    echo 'deb http://apt.hoertech.de bullseye universe' | sudo tee /etc/apt/sources.list.d/openmha.list
    echo 'deb http://aptdev.hoertech.de bullseye universe' | sudo tee /etc/apt/sources.list.d/openmhadev.list
    sudo apt update
    sudo apt install openmha openmha-examples

### 1.2 Removal of Ubuntu development packages

In order to remove openMHA development packages from Ubuntu e.g. to use
a regular openMHA release again on a computer that has been configured
to install development versions,

In Ubuntu 24.04:

    sudo apt-add-repository --remove 'deb [arch=amd64] http://aptdev.hoertech.de noble universe'
    sudo apt purge libopenmha

In Ubuntu 22.04:

    sudo apt-add-repository --remove 'deb [arch=amd64] http://aptdev.hoertech.de jammy universe'
    sudo apt purge libopenmha

In Ubuntu 20.04:

    sudo apt-add-repository --remove 'deb [arch=amd64] http://aptdev.hoertech.de focal universe'
    sudo apt purge libopenmha

On Computers with an ARM CPU running a variant of
Debian, Ubuntu, Raspberry Pi OS, Armbian, or similar:

    sudo rm /etc/apt/sources.list.d/openmhadev.list
    sudo apt update
    sudo apt purge libopenmha

Then check that openMHA is really uninstalled: executing

    mha
    
on the command line must now fail with

    Command 'mha' not found

or a similar error message.  After that, follow the instructions from
file INSTALLATION.md to install the latest released version.

## 2. Source code for development versions

Interested developers can access the development branch on
GitHub: https://github.com/HoerTech-gGmbH/openMHA/tree/development

See file COMPILATION.md for how to set up your build environment to
work with openMHA source code.
