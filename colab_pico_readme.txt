written on August 9, 2023

generating pico uf2 file without software installed on the local computer
we will be using google colab

assumes pico-sdk is uploaded to google drive pico directory
how to upload pico-sdk to colab link --> 
https://petewarden.com/2022/09/20/how-to-build-raspberry-pi-pico-programs-with-no-software-installation/

upload this directory to google drive pico directory
goto colab.google
on left hand side click folder icon
click on google drive icon (wait until it loads)
when you issue command on colab wait until the spinning arrow stops before continuing to next command
colab command is executed using shift return

!sudo apt update
!sudo apt install cmake gcc-arm-none-eabi libnewlib-arm-none-eabi build-essential libstdc++-arm-none-eabi-newlib
cd /content/drive/MyDrive/pico/blink1
!mkdir build
cd build
!cmake ..
!make -j

if build succesfully uf2 should be in MyDrive/pico/blink1/build
download the file and upload to pico by holding white boot button when inserting to usb

if having problem not finding PICO_SDK_PATH issue command
%env PICO_SDK_PATH=../../pico-sdk


