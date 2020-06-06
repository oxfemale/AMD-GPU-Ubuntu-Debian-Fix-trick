# AMD-GPU-Ubuntu-Debian-Fix-trick

# How to Install Last AMD GPU driver on Linux/Unix
```
'      .---------.
'      |.-------.|
'      ||>run#  ||
'      ||       ||
'      |"-------'|etf
'    .-^---------^-. 
'    | ---~   AMiGA|
'    "-------------'
```
' Fukcing hardware, fucking linux, fucking community, thanks all Folks!<br/>
'---------------------------------------------------------------------<br/>
'      And we are go!<br/>
' Use your favorite text editor to open /etc/apt/sources.list. <br/>
' Modify each line to add the contrib and non-free repositories. <br/>
' The end result should look like the example below.<br/>
'like this:<br/>
' ===============================================================<br/>
deb http://deb.debian.org/debian/ buster main non-free contrib<br/>
deb-src http://deb.debian.org/debian/ buster main non-free contrib<br/>
<br/>
deb http://security.debian.org/debian-security buster/updates main contrib non-free<br/>
deb-src http://security.debian.org/debian-security buster/updates main contrib non-free<br/>
' ===============================================================<br/>
' Save and exit. Then, update Apt.<br/>
apt update<br/>
'      Install the AMD Drivers<br/>
' Now, you can install the non-free Linux firmware from the Debian repository.<br/>
' In addition to that, it's a good idea to install several other key <br/>
' Mesa packages to ensure that your system has everything that it needs.<br/>
apt install firmware-linux firmware-linux-nonfree libdrm-amdgpu1 xserver-xorg-video-amdgpu<br/>
' and Install Vulkan if:<br/>
' Vulkan support isn't strictly necessary, but with the widening support that its<br/>
' receiving in the gaming world, it can't hurt to have, and the performance improvements <br/>
' it promises are substantial enough to make it worth using whenever possible.<br/>
' Actually, Wine and Lutris are relying on Vulkan more and more to increase <br/>
' compatibility and performance on a wide range of games. <br/>
' Install Vulkan support with the following.<br/>
apt install mesa-vulkan-drivers libvulkan1 vulkan-tools vulkan-utils vulkan-validationlayers<br/>
'  and maybe some OPENGL, if you still cryptojerk in 2020, ok, be cool, we are all do it time from times<br/>
apt install mesa-opencl-icd<br/>
'  ....and FUUUUCKCK!!! ERROR/WARING ATTACK ON YOU MY FRIEND:<br/>
' OOPS:    .....ntel-microcode: microcode will be updated at next boot<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_mec2.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_mec.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_me.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_pfp.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_ce.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_sdma1.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_sdma.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_uvd.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_vce.bin for module amdgpu<br/>
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_smc.bin for module amdgpu<br/>
' Hey, still no needed drivers, not packages?!, poor little ponny tell me that:<br/>
sudo apt install git -y<br/>
sudo apt update && sudo apt upgrade -y<br/>
cd;git clone https://kernel.googlesource.com/pub/scm/linux/kernel/git/firmware/linux-firmware.git<br/>
cd ~/linux-firmware/amdgpu<br/>
sudo cp * /lib/firmware/amdgpu<br/>
sudo update-initramfs -k all -u -v<br/>
sudo reboot<br/>
' OoOOoOoOOOoOooOO ( LOL, KEK and You Happy very mutch ) OoOOoOoOOOoOooOO<br/>
' IF you still not a happy, drink some beer and install Windows tulen edition or buy SUN Graph station - they cool!<br/>
'<br/>
```
' Art by Elissa Potier
'  .   *   ..  . *  *
'*  * @()Ooc()*   o  .
'    (Q@*0CG*O()  ___
'   |\_________/|/ _ \
'   |  |  |  |  | / | |
'   |  |  |  |  | | | |
'   |  |  |  |  | | | |
'   |  |  |  |  | | | |
'   |  |  |  |  | | | |
'   |  |  |  |  | \_| |
'   |  |  |  |  |\___/
'   |\_|__|__|_/|
'    \_________/
```
