Note: This guide assumes that you are running linux and will include specific instructions for Ubuntu.

1. Install the MPLAB compiler and SCONS software construction tool.
  a. The MPLAB Compiler can be downloaded at http://www.microchip.com/pagehandler/en_us/devtools/mplabxc/ and installing the .run for your OS.
    note: If isntalling on Ubuntu, you must first install 32-bit compatibility libraries using the command "sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0" assuming you are running 13.10 or higher. The .run must also be modified to run, which is possible using "chmod +x some-app.run" which changes permissions of the file, allowing it to execite.
  b. to install the SCONS software, type "sudo apt-get install scons" into your terminal.
    note: You may run into an error when running scons that can be resolved by opening SConstruct and editing line 7, changing '/application/microchip/xc16/v1.25/bin' to '/opt/microchip/xc16/v1.25/bin'.
2. Launch bootloadergui.py located in elecanisms/site_scons/. Plug in your elecanisms board, ensuring that you hold down the black button (SW1) located next to the red button (RES) to notify the bootloader to connect to the host PC.
    note: You may encounter problems launching bootloadergui.py. Download the module located at https://walac.github.io/pyusb/ following the instructions located in the README. You may also need to install the TKinter module using the command "sudo apt-get install python-tk".
3. Compile our blink.c file by typing "scons" in the elecanisms/blink directory. Once you have connected to your elecanisms board within your GUI, navigate to File/import HEX... and select blink.HEX.
4. Press the reset button on the elecanisms board and use SW2 and SW3 to switch between two different frequencies of blink!
