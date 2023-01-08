# Orange Pi 5 Dev
Repository containing information about my current development setup on the Orange Pi 5. Information will include dot files, config directories and steps followed to create the development setup. In future any code written for the Orange Pi 5 will be included here. 

Dot files are stored in Dot_Folders. The following subdirectories exist:

1) .config contains all config files that are located at ~/ (either /root/ or /home/"your_user_name"/) under the directory of the same name.

# Loading The Official Ubuntu OS Image
Please consult the general guide given in Resources/User_Manual for more information.  
The official supported images can be obtained from http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-pi-5.html.  

Generally for this project the Ubuntu images were used. The exact one and version used is supplied at https://drive.google.com/file/d/1qYc-L_b_GagOKwiUZEpWlwF-ujEEbBjK/view?usp=share_link in .7z format.  

The general steps used to flash the image on to a Micro SD card is as follows:

1) Download your chosen distribution image.
2) Install the 7z zip tool. My main distro used to run initial configurations was an Ubuntu 18.04 machine. As such the command **sudo apt install p7zip-full** installed the needed package. Please follow any distro specific steps to obtain the package.
3) Unzip the image with the 7z zip tool using the command **7z x Orangepi5_1.0.8_ubuntu_focal_desktop_xfce_linux5.10.110.7z**.
4) Confirm the download was successful by running a checksum test using the command **sha256sum -c *.sha**.
5) Download Balena etcher tool from https://www.balena.io/etcher/. Specifically the .AppImage.
6) First make sure you have a policy kit installed. I installed two as follows; **sudo apt install policykit-1-gnome** and **sudo apt install mate-polkit-bi**.
7) Balena is aware of a bug that is caused even if a policy kit is installed (https://github.com/balena-io/etcher/issues/1179). However for me it was resolved by running the etcher tool from the CLI in sudo mode as follows **sudo ./balenaEtcher-1.13.1-x64.AppImage**, (This assumes you are in the local directory, else correslt point to it).
8) Follow the basic etching steps given at https://wiki.radxa.com/Zero/getting_started.

You should now have a bootable image. Simply plug it in and start the Orange Pi 5.  
The default users and loging details are:  

1) **root** -> **orangepi** 
2) **orangepi** -> **orangepi**

More configuration options can be view in the manual at Section 3. Personally I only opted to disable automatic desktop login by executing **sudo disable_desktop_autologin.sh**. Further Section 3.4.5 details how to entirely switch off the default desktop environment by entering the Orange Pi 5 config with **sudo orangepi-config**. As I will be using the i3 desktop environment this can and probably should be disabled for performance reasons.

# Loading The Armbian OS Image

Unfortunately as of writing pulseaudio did not work when I used the Orange Pi's Ubuntu image. I am sure it can be fixed or that a reflash would get it running again. Some talk of debugging to see if the audio card is working can be found in Section 3.12. 

1) Clear the SD card by following the steps given at https://www.easeus.com/computer-instruction/format-sd-card-in-linux.html#using_terminal. Essentially use diskmanager to format the partitions and then clear all partitions to have a fresh SD card.
2) Download the armbian image from https://www.armbian.com/orangepi-5/ . I opted to go with Cinnamon desktop but this won't matter since i3 will be installed later.
3) Install xz-utils by using **sudo apt-get install xz-utils** and unzip the image by using the command **unxz ubuntu-19.10-preinstalled-server-arm64+raspi3.img.xz**. Replace ubuntu-19.10... with whichever file you chose to download.
4) Repeat step 5-8 from the previous Ubuntu image's steps. (Etching the image on the SD card).


# Quality Of Life Configurations

1) Unfortunately/Fortunately the Orange Pi 5 runs on arm64 since google chrome is based off of amd64 one can not install it. Either install firefox or use the chromium browser google chrome is based off of. This comes shipped on the image I used.  
In order to enable darkmode follow the steps at https://dev.to/felixdusengimana/how-to-enable-dark-mode-in-chrome-on-ubuntuno-code-apps-themes-2p41.
2) I enabled the universe repository on the main desktop environment by going to Applications->Settings->Additional Drivers. Once the window is open select the Ubuntu Software tab and enable universe. Follow all installation prompts and refresh the repo.



