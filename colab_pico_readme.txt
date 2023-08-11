written on August 9, 2023

generating pico uf2 file without software installed on the local computer
we will be using google colab https://github.com/sonnny/pico_google_colab/edit/main/colab_pico_readme.txt

I preloaded pico-sdk on my google drive to speed up compiling (see note below)

assumes this github is named pico_google_colab directory
assumes pico-sdk is uploaded to google drive pico directory
how to upload pico-sdk to colab link --> 
https://petewarden.com/2022/09/20/how-to-build-raspberry-pi-pico-programs-with-no-software-installation/

upload this directory to google drive pico directory
goto colab.google
on left hand side click folder icon
click on google drive icon (wait until it loads)
when you issue command on colab wait until the spinning arrow stops before continuing to next command
colab command is executed using shift return

cd /content/drive/MyDrive/pico
!sudo apt install cmake gcc-arm-none-eabi libnewlib-arm-none-eabi build-essential libstdc++-arm-none-eabi-newlib
!git clone https://github.com/sonnny/pico_google_colab.git
cd pico_google_colab
mkdir build
cd build
!cmake ..
!make

if build succesfully uf2 should be in MyDrive/pico/pico_google_colab/build
download the file and upload to pico by holding white boot button when inserting to usb
then copy the uf2 file to the rp2 that will appear as a regular usb thumbdrive

if having problem not finding PICO_SDK_PATH issue command
%env PICO_SDK_PATH=../../pico-sdk

remember that PICO_SDK_PATH is already set in CMakeLists.txt
remember after command you need to press shift enter to execute in the browser


