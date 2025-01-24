# Introduction

This document is intended to give instructions on using the [discontinued Sense V2 3D Scanner](https://support.3dsystems.com/s/article/Sense-Scanner?language=en_US) which reached End of Service Life on 31st December 2022

In this repo you will find information on how to get it running on modern systems with open software and drivers, as well as reviews and user guides.

## TLDR; Conclusion
I have been successful in using the stock Windows 8 (32-bit) software on a 64-bit Windows 10 installation. I tried with OpenNI 2 but uninstalled this in favour of the Intel RealSense which made it work for me. The 3D systems software, while not ideal or most up to date still provided OK results and useable files.

I have not had any success in using this scanner on Linux systems. The latest instructions I could find for getting this working were for Ubuntu 18 LTS and older. There also doesn't seem to be much in the way of 3D scanning software available for Linux systems.

# General Information
The Sense V2 was the successor to the consumer focussed V1 which was discontinued in 2015.

A detailed review can be found on the 3D Mag website [here](https://www.3dmag.com/reviews/3d-systems-sense-2-realsense-sr300-review/) and may contain more valuable information about the platform.

As previously mentioned, this hardware reached End of Service Life in 2022. As such, support is dwindling for the platform.

The Sense V2 is a repackaged Intel RealSense Camera SR300 which is how Windows recognises the scanner in Device Manager.

## Specification
This specification is from the [V2 user manual](Sense2_UserGuide.pdf)


|||
|---|---|
**Size**| 12.9 x 17.8 x 3.3 cm (W x H x D)
**Supported operating systems**: | Windows 10 64-bit
**Depth image size**:| 640(w) x 480(h) px
**Color image size**:| 1920(w) x 1080(h) px
**Spatial x/y resolution at 0.5 m**:| 0.9 mm
**Depth resolution at 0.5 m**:| 1 mm
**Operating temperature**:| 10 - 40° C
**Data interface**:| USB 3.0
**USB cord length**:| 2m
**Maximal image throughput**:| 30 fps
**Scan volume**
Min:| 0.2 m x 0.2 m x 0.2 m
Max:| 2 m x 2 m x 2 m
**Operating range**
Min:| 0.2 m
Max:| 1.6 m
**Field of view**
Horizontal:| 45°
Vertical:| 57.5°
Diagonal:| 69°
**Hardware recommendations**
Processor:| Intel Core i5 5th Gen or newer
RAM:| 2 GB minimum
Screen Resolution:| 1280 x 1024 minimum
Disk Space:| 4 GB available hard disk space
**Warranty**:| 1 year

# Software

## 3D Systems Software
The Sense software is still available to download on the [3D Systems website](https://support.3dsystems.com/s/article/Sense-Scanner?language=en_US)

Some users have reported that the Windows 10 software no longer works, but that the 32-bit Windows 8 software does. This can be installed on Windows 10 as well and can be found on the same page linked above.

You may need to update the drivers for the scanner by uninstalling the initial drivers and disconnecting/reconnecting the scanner.

# Alternate Software
There have been reports that the Sense Software by 3D Systems is laggy and slow, and several Reddit users have reported success using the OpenNI 2 SDK Binaries in conjunction with Skanect software which reportedly produce better results than the original software.

As the hardware ages and paid software continues to be developed, support will slowly dissapear for this hardware. More recently it has  been reported that Skanect no longer functions properly with the Sense V2.

There are other softwares that have previously worked but are now abandoned by developers and so they haven't been explored here.

# Drivers

The scanner is recognised as an SR300 when connected to Windows. There should be 3 components recognised when connected.

- Intel(R) RealSense(TM) Camera SR300 Depth
- Intel(R) RealSense(TM) Camera SR300 RGB
- Intel(R) RealSense(TM) Camera SR300 Virtual Driver

If these aren't all available it won't work properly. Uninstalling the drivers that are present and then disconnecting and re-connecting the scanner should trigger Windows update to download the latest drivers.
[librealsense github issue](https://github.com/IntelRealSense/librealsense/issues/12926)

There is a video on the 3D Systems website detailing how to properly update the Sense 2 scanner [here](https://support.3dsystems.com/s/article/Sense-2-Driver-Update-Win-10?language=en_US) though it's expected to be wildly out of date.


## IntelRealSense SDK
[librealsense github](https://github.com/IntelRealSense/librealsense)

I believe this is the SDK that I used in order to get things running. This in conjunction with the Windows 8 32-bit software from 3D Systems available on their page. 

## OpenNI 2 SDK Binaries
Some users have reported success using OpenNI 2 SDK, however I don't believe this worked for me with Windows 10.

Latest versions can be found for download on [Structure.io](https://structure.io/openni/)

The Windows version of the binaries include a Windows driver. Linux and macOS versions do not require additional drivers.

While OpenNI themselves no longer maintain their repository for OpenNI2, Structure have forked the repository and are maintaining it [here](https://github.com/structureio/OpenNI2) should you wish to explore the source code or raise an issue.

# Modifications
A pistol-style handle has been developed to swap out the original. these were uploaded to [Prusia Printables](https://www.printables.com/model/15656-3d-systems-sense-v1-v2-3d-scanner-replacement-chas/files) by [Ubermeisters](https://www.printables.com/@Ubermeisters) in 2019.
[Files](3d-systems-sense-v1-v2-3d-scanner-replacement-chassis-model_files) have been reproduced in this repository under the Creative Commons License.

# Developing for the Sense V2
I have not developed anything for this scanner, but from what I've read the best way to go about it is with IntelRealSense SDK.

# On the Web
- [3D Mag Sense V2](https://www.3dmag.com/reviews/3d-systems-sense-2-realsense-sr300-review/) goes through the differences between V1 and V2, quality of imagery, and some user tips
- [3D Systems Information Page](https://support.3dsystems.com/s/article/Sense-Scanner?language=en_US) contains user manuals and software downloads
- There are various Reddit posts about using this scanner since its discontinuation and can be found by searching for "3D Systems Sense V2" on Reddit
