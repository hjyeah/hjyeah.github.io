---
layout:     post
title:      "android真机调试说明"
subtitle:   "主要针对android真机调试的相关方面，翻译自android developer官网"
date:       2016-04-19
author:     "hj_yeah"
header-img: "img/post-bg-android-hardware.jpg"
tags:
    - android
---

> 翻译来源：[using hardware devices](http://developer.android.com/tools/device.html) 

一.启动设备上的开发者选项   
To access these settings, open the Developer options in the system Settings. On Android 4.2 and higher, the Developer options screen is hidden by default. To make it visible, go to Settings > About phone and tap Build number seven times. Return to the previous screen to find Developer options at the bottom.

在 Android 4.2版本一下的设备自带开发者选项菜单，而对于Android 4.2版本及以上版本的设备，开发者选项默认是隐藏的，通过 设置 > 关于手机， 然后点击版本号7次， 回退到之前的屏幕界面则会显示开发者选项

二.设置设备的相关配置（开发前）    
Before you can start, there are just a few things to do:    
1.Verify that your application is "debuggable" in your manifest or build.gradle file.   
  In the build file, make sure the debuggable property in the debug build type is set to true.The build type property overrides the manifest setting.    

	  android {
    	buildTypes {
        	debug {
            	debuggable true
        	}   


  In the AndroidManifest.xml file, add android:debuggable="true" to the <application> element.    
  
> Note: If you manually enable debugging in the manifest file, be sure to disable it in your release  build (your published application should usually not be debuggable).     

2.Enable USB debugging on your device by going to Settings > Developer options.    
  Note: On Android 4.2 and newer, Developer options is hidden by default. To make it available, go to Settings > About phone and tap Build number seven times. Return to the previous screen to find Developer options.

3.设置对应OS系统检测设备
  。windows平台上，需要安装USB driver for adb，关于安装引导以及链接OEM drivers，具体点击[OEM USB Drivers](http://developer.android.com/tools/extras/oem-usb.html)
  。MAC OS X平台，可以直接跳过
  。Ubuntu Linux平台，具体参照原文链接[Linux for android](http://developer.android.com/tools/device.html)

Note: When you connect a device running Android 4.2.2 or higher to your computer, the system shows a dialog asking whether to accept an RSA key that allows debugging through this computer. This security mechanism protects user devices because it ensures that USB debugging and other adb commands cannot be executed unless you're able to unlock the device and acknowledge the dialog. This requires that you have adb version 1.0.31 (available with SDK Platform-tools r16.0.1 and higher) in order to debug on a device running Android 4.2.2 or higher.

If using Android Studio, run or debug your application as usual. You will be presented with a Device Chooser dialog that lists the available emulator(s) and connected device(s). Select the device upon which you want to install and run the application.

If using the Android Debug Bridge (adb), you can issue commands with the -d flag to target your connected device.

三.USB厂商ID    
      
This table provides a reference to the vendor IDs needed in order to add USB device support on Linux. The USB Vendor ID is the value given to the ATTR{idVendor} property in the rules file, as described above.     
以下列表展示了相应手机厂商的ID（针对linux开发平台上）   

| *Company* | *USB_Vendor_ID* |
| Acer | 0502 |
| ASUS | 0b05 |
| Dell | 413c |   
| Foxconn | 0489 |
| Fujitsu | 04c5 |
| Fujitsu | Toshiba	04c5 |
| Garmin-Asus | 091e |
| Google | 18d1 |
| Haier | 201E |
| Hisense | 109b |
| HTC | 0bb4 |
| Huawei | 12d1 |
| Intel | 8087 |
| K-Touch | 24e3 |
| KT Tech | 2116 |
| Kyocera | 0482 |
| Lenovo | 17ef |
| LG | 1004 |
| Motorola | 22b8 |
| MTK | 0e8d |
| NEC | 0409 |
| Nook | 2080 |
| Nvidia | 0955 |
| OTGV | 2257 |
| Pantech | 0a9 |
| Pegatron | 1d4d |
| Philips | 0471 |
| PMC-Sierra | 04da |
| Qualcomm | 05c6 |
| SK Telesys | 1f53 |
| Samsung | 04e8 |
| Sharp | 04dd |
| Sony | 054c |
| Sony Ericsson | 0fce |
| Sony Mobile Communications | 0fce |
| Teleepoch | 2340 |
| Toshiba | 0930 |
| ZTE | 19d2 |



