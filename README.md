# Nvidia-Driver-update-Resolution-fix

I know most of you might have run down the same problem when you have installed nvidia drivers on to your laptop mostly this problem comes to the linux user. it basically happens because the drivers mess with the DPI(DPI, or dots per inch, is a measure of the resolution of a printed document or digital scan. The higher the dot density, the higher the resolution of the print or scan. ) of the screen. So I have searched on net and came up with a small simple hack.


# Just follow this discussion and you will understand what is to be done.

[Nvidia Forum Discussion](https://forums.developer.nvidia.com/t/edid-issue/44370)

IT is really a very simple technique.
## Step 1

navigate to /etc/X11/xorg.conf.d directory
	
	cd /etc/X11/xorg.conf.d

## Step 2

check if your find any nvidia.conf file in there, if you dont find any just run this command 
	
	nvidia-xconfig 

in the terminal this will create a xorg.conf fill in the direcotry /etc/X11/xorg.conf.d

## Step 3

Now just open the xorg.conf or nvidia.conf file using your favourite text editor and navigate to this section which says Section "Device" and now add the two line under the driver "nvidia" section as shown below

	Section "Device"
	    Identifier  "Videocard0"
	    Driver      "nvidia"
		Option      "UseEdidDpi" "False"
		Option      "DPI" "96 x 96"
	EndSection

## Step 4

save the file and now reboot you system the resolution problem will be fixed.

Thank you for reading this solution
