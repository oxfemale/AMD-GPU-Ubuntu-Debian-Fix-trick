# AMD-GPU-Ubuntu-Debian-Fix-trick

# How to Install Last AMD GPU driver on Linux/Unix
'
'      .---------.
'      |.-------.|
'      ||>run#  ||
'      ||       ||
'      |"-------'|etf
'    .-^---------^-.
'    | ---~   AMiGA|
'    "-------------'
'
' Fukcing hardware, fucking linux, fucking community, thanks all Folks!
'---------------------------------------------------------------------
'And we are go!

' Use your favorite text editor to open /etc/apt/sources.list. 
' Modify each line to add the contrib and non-free repositories. 
' The end result should look like the example below.

'like this:
' ===============================================================
deb http://deb.debian.org/debian/ buster main non-free contrib
deb-src http://deb.debian.org/debian/ buster main non-free contrib

deb http://security.debian.org/debian-security buster/updates main contrib non-free
deb-src http://security.debian.org/debian-security buster/updates main contrib non-free
' ===============================================================
' Save and exit. Then, update Apt.
apt update

'      Install the AMD Drivers
' Now, you can install the non-free Linux firmware from the Debian repository.
' In addition to that, it's a good idea to install several other key 
' Mesa packages to ensure that your system has everything that it needs.
apt install firmware-linux firmware-linux-nonfree libdrm-amdgpu1 xserver-xorg-video-amdgpu

' and Install Vulkan if:
' Vulkan support isn't strictly necessary, but with the widening support that its 
' receiving in the gaming world, it can't hurt to have, and the performance improvements 
' it promises are substantial enough to make it worth using whenever possible.
' Actually, Wine and Lutris are relying on Vulkan more and more to increase 
' compatibility and performance on a wide range of games. 
' Install Vulkan support with the following.
apt install mesa-vulkan-drivers libvulkan1 vulkan-tools vulkan-utils vulkan-validationlayers

'  and maybe some OPENGL, if you still cryptojerk in 2020, ok, be cool, we are all do it time from times
apt install mesa-opencl-icd

'  ....and FUUUUCKCK!!! ERROR/WARING ATTACK ON YOU MY FRIEND:
' OOPS:    .....ntel-microcode: microcode will be updated at next boot
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_mec2.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_mec.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_me.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_pfp.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_ce.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_sdma1.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_sdma.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_uvd.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_vce.bin for module amdgpu
' OOPS:    W: Possible missing firmware /lib/firmware/amdgpu/vega20_smc.bin for module amdgpu
' Hey, still no needed drivers, not packages?!, poor little ponny tell me that:
sudo apt install git -y
sudo apt update && sudo apt upgrade -y
cd;git clone https://kernel.googlesource.com/pub/scm/linux/kernel/git/firmware/linux-firmware.git
cd ~/linux-firmware/amdgpu
sudo cp * /lib/firmware/amdgpu
sudo update-initramfs -k all -u -v
sudo reboot

' OoOOoOoOOOoOooOO ( LOL, KEK and You Happy very mutch ) OoOOoOoOOOoOooOO
' IF you still not a happy, drink some beer and install Windows tulen edition or buy SUN Graph station - they cool!
'
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
'
