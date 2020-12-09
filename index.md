# Xilinx Video SDK
The Xilinx Video SDK includes all of the software required to run accelerated video decoding, scaling, and encoding on an AWS V1 instance or an on-premise U30 plaform.  The documentation in this guide covers:

1. Installing all required software
2. Installing firmware for on-premise hardware
2. Verifying your installed software and hardware are working properly
3. Using FFmpeg command line with acceleration enabled
4. Using a launcher to schedule the transcoding of multiple input files
5. Integrating the low-level XiLinx Media Accelerator API with a custom multi-media framework

## Installing the Xilinx Video SDK software
The Xilinx Video SDK is comprised of a number of software packages that interoperate together to form a complete software stack.  The simplest way to install the Xilinx Video SDK is to use the package manager provided with your Linux distribution along with pre-built repositories.  The instructions that follow are tailored for specific operating systems.  Make sure to following the instructions that apply to your setup.

### Ubuntu 18.04 Installation Instructions
To install the Xilinx Video SDK on an Ubuntu 18.04 system, please follow these steps:
    
    sudo apt-get update
    sudo apt-get install curl python
    curl -s --compressed "https://jnicholsxilinx.github.io/video-sdk-test/KEY.gpg" | sudo apt-key add -
    sudo curl -s --compressed -o /etc/apt/sources.list.d/vdk.list "https://jnicholsxilinx.github.io/video-sdk-test/ubuntu/bionic/vdk.list"
    sudo apt-get update
    sudo apt-get install xcdr

The above commands are needed to:
1. Ensure your APT repositories are up to date
2. Install a few dependent packages (curl and python)
3. Add a GPG key needed to validate the supplied packages are authentic
4. Add a new APT repository
5. Update your APT repository to ensure it is up to date following the addition of the new APT repository
6. Install the top-level package called "xcdr" which is also known as the Xilinx transcoder

### RHEL/CentOS 7 Installation Instructions
TODO

### Amazon Linx 2 Installation Instructions
TODO

### Installing Firmware for On-Premise Hardware
TODO

## Verifying the Installation
To verify all software and hardware are working properly, please follow these steps:

    # sudo permissions will be required to start the Xilinx Resource Manager (XRM) service
    source /opt/xilinx/xcdr/setup.sh
    
    # This command will transcode H.264 content to HEVC sending the results to the bit bucket
    ffmpeg -c:v mpsoc_vcu_h264 -i <your-content.mp4> -c:v mpsoc_vcu_hevc -y /dev/null

## Using FFmpeg Command Line with Acceleration
TODO

## Using the Launcher utility to schedule processing of multiple files
TODO

