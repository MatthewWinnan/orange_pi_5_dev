# Orange Pi 5 Dev
Repository containing information about my current development setup on the Orange Pi 5. Information will include dot files, config directories and steps followed to create the development setup. In future any code written for the Orange Pi 5 will be included here.  

# Loading The OS Image
Please consult the general guide given in Resources/User_Manual for more information.  
The official supported images can be obtained from http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-pi-5.html. 
Generally for this project the Ubuntu images were used. The exact one and version used is supplied at Resources/Linux_Image in .7z format.
The general steps used to flash the image on to a Micro SD card is as follows:

1) Download your chosen distribution image.
2) Install the 7z zip tool. My main distro used to run initial configurations was an Ubuntu 18.04 machine. As such the command **apt install p7zip-full** installed the needed package. Please follow any distro specific steps to obtain the package.
3) Unzip the image with **7z x Orangepi5_1.0.8_ubuntu_focal_desktop_xfce_linux5.10.110.7z** 

