## Ecco come abbiamo realizzato DecriptOS!

First thing, in a "Debian Bullseye"-based VM, we created the DecriptOS working environment, configuring all the tools, menus, graphics, features, and downloading the installation files we want to be in the distro.
Then we installed the pre-requisites to start the iso creation phase.
```
sudo apt install live-build squashfs-tools syslinux-common syslinux-utils xorriso isolinux
```
so we created a folder in which to go and put all the files for creating the iso, called `distro`.
```
mkdir distro
```
then we placed our terminal in this folder
```
cd distro
```
and we set the parameters of our iso.
```
lb config -b iso --cache true --apt-recommends true -a amd64 --binary-images iso --debian-installer live --linux-flavours amd64 --mode debian --debian-installer-gui true --archive-areas "main contrib non-free" --security true --win32-loader false --interactive shell --updates true --iso-application decriptOS --iso-publisher https://decripto.org --iso-volume decripto --memtest none --bootloaders grub-efi --binary-filesystem fat32 --bootloaders grub-legacy --bootloaders grub-pc --bootloaders syslinux
```
Finally, obtaining root permissions with this command
```
sudo -s
```
we can start creating the distro development environment (this may take a while)
```
lb build
```
Once we finish this step, we have a super minimal version of Debian to work on and in which to install and configure what we need.

First we install the packages we want in our distro from the official debian repositories
```
apt install cinnamon python3 python3-full python3-pip python3-virtualenv git firefox-esr qtqr kleopatra scdaemon keepassxc zulucrypt-gui printer-driver-all searchmonkey firmware-linux firmware-linux-nonfree firmware-misc-nonfree linux-image-amd64 linux-headers-amd64 firmware-iwlwifi squashfs-tools syslinux-common syslinux-utils xorriso isolinux wireshark gedit simplescreenrecorder kate libreoffice curl tor unzip macchanger iptables libportaudio2 flameshot gimp httrack mousepad httraqt stacer autopsy secure-delete ffmpeg vlc libsecp256k1-0 evince python3-tk hashcat libwxgtk3.0-gtk3-0v5 gir1.2-gtop-2.0 libc++1 shotwell libgconf-2-4 librsvg2-bin firmware-atheros firmware-realtek firmware-amd-graphics clementine audacity dragonplayer viewnior flowblade gufw zenity software-properties-common obs-studio synaptic gdebi firmware-b43-installer firmware-amd-graphics intel-microcode firmware-realtek firmware-atheros firmware-libertas firmware-brcm80211 grub-efi npm mpg123 redshift redshift-gtk ntp firmware-realtek firmware-atheros firmware-bnx2 firmware-bnx2x firmware-brcm80211 firmware-ipw2x00 firmware-intelwimax firmware-libertas firmware-netxen firmware-zd1211 b43-fwcutter firmware-b43-installer firmware-b43legacy-installer firmware-intel-sound firmware-sof-signed mesa-va-drivers intel-microcode i965-va-driver-shaders intel-media-va-driver-non-free inkscape linux-headers-5.10.0-23-amd64
```
At this point, we have to copy all the files with the configurations we might need, running the `skelcopy.sh` script in another terminal window.
This will copy everything needed in the operating system folders and user customizations to the appropriate /etc/skel folder.

Now we can create our user, who will be called `decripto` and for whom we will use the password `decripto`.
```
adduser decripto
```
In order to use the sudo command for operations requiring administrative privileges, we add the `decripto` user to the sudoers by editing the /etc/sudoers file.
```
nano /etc/sudoers
```
adding this line
```
decripto ALL=(ALL:ALL) ALL
```
below the line
```
root ALL=(ALL:ALL) ALL
```
In the sudoers file, we also add the following line, so that the `mac_random.sh` script can assign us a random mac address at each startup without requiring the decripto user's password.
```
decripto ALL=(ALL) NOPASSWD: /home/decripto/Tools/mac_random.sh
```
Then, we make sure that the tor service is not on by default (to avoid conflicts with the prearranged anonymous proxy) and enable the firewall at startup.
```
systemctl disable tor
systemctl enable ufw
```
We install all the other tools by starting the script `scripts.sh`, delete the script, and finally finish by typing
```
exit
```
Now all we have to do is wait for the process to finish (depending on the power of the processor it may take a few minutes).
Eventually, if there were no errors, we will find the .iso file in the distro folder we created.
In order for the iso to be recognized by programs such as Balena Etcher or Rufus and be able to be flashed to a USB, we use the command
```
isohybrid DecriptOS.iso
```
Have fun!