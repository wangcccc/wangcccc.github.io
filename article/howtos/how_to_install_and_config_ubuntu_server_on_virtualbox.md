# How to install & config Ubuntu server on VirtualBox

## Install

1. Create a new virtual machine.
2. In Settings > Storage > Controller: IDE > Empty, select the iso file of Ubuntu server.
3. Start the VM and follow the guide to install.
    * Select the proper mirror server to speed up download speed. (e.g., *<http://mirrors.aliyun.com/ubuntu/>*)
4. Install the updates or just reboot to finish.

## Config

### How to change timezone?

    # list zoneinfos
    ls /usr/share/zoneinfo
    # link the localtime to the timezone you want to set
    sudo ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

### How to change the terminal resolution?

1. Add the following three settings to `/etc/default/grub`:

        GRUB_GFXMODE=1280x1024
        GRUB_CMDLINE_LINUX_DEFAULT="nomodeset"
        GRUB_GFXPAYLOAD_LINUX=keep

2. Followed by running:

        sudo update-grub
        sudo reboot

### How to change the font and font size?

Run the following command and then follow the configuration guide.

    sudo dpkg-reconfigure console-setup

### How to change apt mirror?

Apt mirror is configed in */etc/apt/sources.list*

    sudo sed -i 's/http:\/\/us.archive.ubuntu.com\/ubuntu\//http:\/\/mirrors.aliyun.com\/ubuntu\//' /etc/apt/sources.list

### How to install updates?

    sudo apt update        # Fetches the list of available updates
    sudo apt upgrade       # Installs some updates; does not remove packages
    sudo apt full-upgrade  # Installs updates; may also remove some packages, if needed
    sudo apt autoremove    # Removes any old packages that are no longer needed

### How to enable shared clipboard?

For a GUI-less server the shared clipboard functionality of Virtual Box **can not work**. A text-based server does not have a clipboard.

We may still want to install guest additions in an Ubuntu server for the following features they provide:

* Shared folders using `vboxsf` filesystem
* Time sync with the host
* generic host-guest communication via `VBoxManage guestproperty`
* automatic guest logon (passing credentials on booting the VM)

### How to install Guest Additions?

    sudo apt-get install virtualbox-guest-additions-iso

### How to enable shared folders?

1. Make sure that Guest Additions are properly installed.
2. In Settings > Shared Folders > Machine Folders, create and config a new shared folder.
3. Start the VM, the shared folder shall be auto mounted to `/media/sf_{SharedFolderName}`
