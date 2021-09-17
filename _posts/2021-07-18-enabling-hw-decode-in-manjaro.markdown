---
layout: category-tutorial
title:  "Enabling Hardware decoding in Chrome/Chromium browser on Manjaro"
date:   2021-07-19 14:24:56 +0530
categories: tutorials
---

Install chrome or chromium

1. Create a file named chrome-flags.conf in you .config folder
	```
	touch ~/.config/chrome-flags.conf
	```

(If you are using chromium make a file named `chromium-flags.conf` instead)

2. Populate the file with this
```
	--ignore-gpu-blocklist
	--enable-gpu-rasterization
	--enable-zero-copy
	--enable-features=VaapiVideoDecoder
```
3. a. Check if vaapi drivers are installed

	```
	Vainfo
	``` 
	(If you get command not found install vainfo with `sudo pacman -S libva-utils`)

	Look for 
	```
vainfo: VA-API version: 1.12 (libva 2.11.1)
vainfo: Driver version: Splitted-Desktop Systems VDPAU backend for VA-API - 0.7.4
	```

	b. Check if vdpau drivers are installed
	```
	vdpauinfo
	```
	(If you get command not found install `sudo pacman -S vdpauinfo`)

	Look for:
```
	display: :1   screen: 0	API version: 1
	Information string: NVIDIA VDPAU Driver Shared Library 470.42.01
```
If you're using nouveau drivers configure va-api if your using proprietary drivers configure vdpau.

4. Check which drivers you are using
```
	lspci -k | grep -EA3 'VGA|3D|Display'
```

	Look for

	```
	Kernel driver in use: nvidia/nouveau
	```

5. a. Configure va-api
```
	env $LIBVA_DRIVER_NAME=nouveau
```
b. Configure vdpau
```
	env $VDPAU_DRIVER=nvidia
```

Finally install `libva-vdpau-driver-chromium` or `libva-vdpau-driver-vp9-git` from AUR.

(to enable AUR go to add/remove software > Preferences > Third party > enable AUR. After enabling AUR I would recommend to install yay with `sudo pacman -S yay`)

	yay -S libva-vdpau-driver-chromium
	Or
	yay -S libva-vdpau-driver-vp9-git

Since chrome 90+ chrome has removed support for vp9 hardware decoding so install the [H264ify Chrome Extension](https://chrome.google.com/webstore/detail/h264ify/aleakchihdccplidncghkekgioiakgal?hl=en) .

To check if hardware acceleration for videos is enabled, play a youtube video and press `ctrl+shift+i`.

![ss1](https://i.imgur.com/pBF4XO2.png)

From the hamburger menu in the top right > more tools > media and see if the youtube video shows `Hardware decoder = true`

![ss2](https://i.imgur.com/JxoZz8a.png)

Thats it!

