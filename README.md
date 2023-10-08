# SV04-Touchscreen
SV04 Touchscreen Source (DGWIN HMI)

# Project Structure
**DWIN_SET**

Folder containing the project Files for the HMI (display) device.
The generated binaries needed to flash the device are also placed here.

**images**

Folder containing the Photoshop (psd) files used to generate (some) of the 
images. The actual JPEG (jpg) files are also saved here.
Please note that the file names are important (e.g. the digits in 32_main
and 0.jpg have significant values that follow the requirements of DGWIN).

**TFT**

DGWIN Project-related files

**DWprj.hmi**

Project files. Please use DGUS application to open/edit the project


# How to
1. Download the DGUS application/IDE from their official site:
https://www.dwin-global.com/uploads/DGUS_V7646.zip

A copy of the zip is available in the Resources folder in case their site isn't available
but try to get their latest version from their site.

Extract the contents to your drive. Any location will do.

1. Also, download the fonts used in the screens:
https://fontsgeek.com/fonts/Geneva-Regular

1. If you want to to change the UI or create new screens, create or edit the images first.
Preferrably use psd files so it is editable later. Then generate the jpeg files.
Save the files in the images folder.

1. Open the DWprj.hmi in the IDE
The IDE is named as "DGUS_VXXXX.exe".

1. In the Welcome tab, click the ICL generator.

1. In the ICL generator, select the folder or images.
Then click Generate ICL.
Save the ICL in the DWIN_SET folder.

> Please note that the numbers in the filenames have significance. Follow the guides from DGWIN.
> For example, "32" onwards indicates background images; and "48" is the starting number for icons.
> The display device have special sections of available memory, and these numbers indicates those sections.
> While you can customize them to some degree, please check that you are within the DGWIN specifications.

1. In the Welcome tab, you can also use the Config editor.
You can open and edit the existing one if need to change anything: DGWIN_SET\T5LCFG_272480.CFG

1. Back in DGUS main IDE, select the pages (jpg files) on the left panel and edit the UI controls.
If you created a new page, add that page (jpg) file first.

1. Then click Save and Generate.

1. Copy the contents of DGWIN_SET folder, except for the jpg files to your SD Card.
Save those files inside DGWIN_SET folder in the root of the card.
Use this to flash the display device.

# About SD Cards
1. Format your SD Card to FAT32 and with allocation: 4096KB 
IMPORTANT: Using a different allocation (i.e. 32) will not be compatible with the display device

# Serial Command (VP) Codes and Addresses
The screen firmware MUST match the board's (Marlin) firmware.
In the Marlin code, please refer to the following file for the VP command codes and data addresses:
\Marlin\src\lcd\e3v2\creality\LCD_RTS.h

For example:
VP 0x1036 : E0 Nozzle Temp
VP 0x1052 : E1 Nozzle Temp

