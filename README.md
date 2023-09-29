# DecriptOS

Welcome to DecriptOS, the Operating System that puts your privacy, cybersecurity, and the world of crypto at the center of your interests. With DecriptOS, you will have access to a lightweight, fast and powerful Linux distro that will allow you to take full advantage of the potential of emerging technologies.

Our priority is your privacy. With DecriptOS, you can browse securely using pre-configured TOR and taking advantage of our mac spoofing service that runs automatically at startup to create a new virtual computer each time you boot up. In addition, we have included Brave and Firefox as browsers, already configured to provide security, privacy and simplify crypto management.

Speaking of crypto, DecriptOS is your ally. We have included all the tools you need:
- crypto wallets such as Wasabi, Electrum, Feather and others;
- browser extensions;
- Linux package manager to search for new tools
all made public and transparent, via GitHub, to encourage open source development.

For information protection and security, DecriptOS is at the forefront. We have configured Firefox with preset bookmarks to avoid phishing sites and included dedicated tools for due diligence of crypto projects, including some created by our team. In addition, KeepassXC is included as a password manager to ensure maximum security for your credentials.

And let's not forget productivity! We have integrated LibreOffice for your productivity needs, video recording tools such as OBS and SimpleScreenRecorder, and even a video editor such as Flowblade. In addition, we have included Obsidian to simplify the management of notes and data collection in due diligence.

DecriptOS is designed to be easy to use and adaptable to your needs. You can run it directly from a USB stick, without risk to your main operating system files. In addition, we have included system shortcuts to create templates for work and custom commands to simplify your daily tasks.

The best thing about DecriptOS? It is completely customizable! We can create dedicated, customized builds for you to best meet your specific needs.

Don't risk your privacy and crypto security. Switch to DecriptOS and experience an operating system dedicated to privacy, crypto, and cybersecurity like never before.

Discover DecriptOS, your new partner in web3.

## Features

- **Specialized Tools**: DecriptOS includes a wide range of preinstalled tools specifically for cryptocurrency and Web3 investigations. You'll find: blockchain explorers and analyzers, Ethereum clients, smart contract scanners and more.

- **Safe environment**: The distro has been configured to provide a secure, isolated and privacy-aware environment.

- **Frequent updates**: DecriptOS is constantly maintained and updated by the Decripto.org development team. Users will receive regular security updates and new features to stay up-to-date with developments in cryptocurrency and Web3.

## System Requirements

To use DecriptOS, your system, or your Virtual Machine, must meet the following minimum requirements:

- CPU: 1 GHz or higher
- RAM: 2 GB or more
- Disk space: 20 GB or more (in case of Virtual Machines)
- USB capacity (if you want to use via reboot): 8 GB or more
- Internet connection for updates and downloads of additional resources

## Startup or Install

To start or install DecriptOS, follow the steps below:

1. Download the ISO image of DecriptOS (version 2.7) from [this link](https://e.pcloud.link/publink/show?code=XZPd2WZHBn0zbo03vJ02sJ679vDs4SOVRwX)
2. Create a bootable installation device (e.g., a USB stick or Virtual Machine) using the ISO image

   2.1 Flashing the .iso file to USB for use via reboot:

    - A USB flash drive (with a minimum capacity of 8Gb)
    
    - Download this software [Rufus](https://rufus.ie/it/) (in case you are running this procedure on Windows)

    or download [Unebootin](https://unetbootin.github.io/) (if you are on Mac Os):

    - once downloaded press the right button and click on "Open" (you may need to do this a couple of times)

    - then select the .iso file and the USB device

    - and start the process.

3. Boot your computer (or Virtual Machine) using the installation media, holding down `Alt` (if on Mac OS) or `esc` or `F12` (if on Windows).

   - from Mac select `EFI Boot`:

   - from Windows select `USB - UEFI OS`:

   3.1. If you boot the computer via BIOS with `F2` go to the tab `Save & Exit` and select the USB flash drive named `UEFI`

4. From the boot menu choose "Live system" to try the distro (recommended) or "Start installer" to start the installation on the computer following the instructions.

   4.1. If you decide to install the operating system (like on an old computer), please set `decripto` as username, otherwise some tools may not work properly.
   
## Steps to do after system startup (live)

1. Set a password for the keyring from the terminal with `sudo passwd` and then enter it (if desired). The other default passwords are `decripto`.
2. Connect to WiFi (if from USB)
3. Check the date and time, if necessary, synchronize the operating system with the current time zone.
4. Update the operating system, in the terminal type `sudo apt update`, hit enter, enter the password (`decripto` by default) hit enter, when finished type `sudo apt upgrade` and hit enter, if needed when prompted type `yes` for additional packages.
5. Configure your credentials on git by going to the terminal and typing `git config --global user.name "Your Name"` then `git config --global user.email your@email.com`.
 

## Disclaimer

DecriptOS is provided "as is" and without warranty of any kind, express or implied, including, but not limited to, warranties of saleability, suitability for a particular purpose, and non-infringement. In no event shall the developers of DecriptOS be liable for any claims, damages, or other liabilities, whether in action of contract, negligence, or otherwise, arising out of, or in connection with, the distribution or use of DecriptOS or other DecriptOS-related business.

---

**Note:** Since it is still in the testing phase, if you find anomalies or notice that something is missing or would like to add something by default, click at the top of the `Issues` tab and create a new issue (a memo) explaining what you found or what to fix.

**License:** In the [LICENSE](https://github.com/Decripto-org/DecriptOS/blob/main/LICENSE) file you will find all the details about the license of use.

