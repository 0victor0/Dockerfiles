#Full screen on Virtualbox

In case you're running Docker in a guest on Virtualbox, Here are the commands to get full screen on Virtualbox guest machine. Make sure you "insert" the guest addtions CD.

        sudo apt-get install virtualbox-guest-dkms virtualbox-guest-source virtualbox-guest-utils virtualbox-guest-x11
        sudo apt-get install dkms build-essential linux-headers-3.16.0-4-all
        sudo apt-get dist-upgrade
        cp /media/cdrom/VBoxLinuxAdditions.run
        chmod 755 VBoxLinuxAdditions.run
        sudo ./VBoxLinuxAdditions.run

#For accessing shared folders

        sudo usermod -aG vboxsf <youruser>  #in the guest machine
                                            #log out then log in
