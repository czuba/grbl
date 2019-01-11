##TBC:  Terminal method described below is most reliable method of compiling/installing grbl on Arduino Uno.

(...using Arduino IDE involves somewhat opaque library updating restart sequence that seems potentially error prone).


------------------From:  [the original Grbl wiki](https://github.com/gnea/grbl/wiki/Compiling-Grbl) ------------------
For Mac OS X:
Based on last update by: 2012-01-29 by chamnit. (Tested on OS X 10.7, 10.6, 10.4 and the Arduino IDE r22,v1.0)
	...revised from memory by TBC 2019-01-11  (used with OS X 10.13 & Arduino IDE 1.8.1)

#### Install & setup dependencies:
This method of compiling Grbl uses the Mac OSX terminal and command line to access the Arduino IDE's compilers without having to use the Arduino IDE. This produces the same firmware as the Arduino IDE method above.
- First, you'll need to make sure you have the most up-to-date Arduino IDE version installed on your Mac. The trickiest part is setting up the environment path for the compilers included in the Arduino software. To do this, you'll need to first locate where they are. Depending on where you place your Arduino.app software, this will usually be located in /Applications/Arduino.app for most people. The complete path is then: /Applications/Arduino.app/Contents/Java/hardware/tools/avr/bin/
- To add the compiler path: Open the Terminal.app in /Applications/Utilities.
- Then type: `nano ~/.bash_profile` to edit your shell config file.
- Now add the following to the end of the file:
```
export PATH=$PATH:/Applications/Arduino.app/Contents/Java/hardware/tools/avr/bin
```
	- _(assuming you installed Arduino in the default location...if you didn't, modify as needed)_
- Press Crtl-X to exit and select Yes to save the file. Now you have added the compiler path. *You will need to close the current working window and re-open a new one for the path to be loaded correctly.*

- Install optiboot

#### Compile Hex for loading onto Arduino:

Once your Terminal paths are setup, all you will need to do is:
- Open a new Terminal & go to your grbl directory
- Type `make`
		- _Note: To clear all of the old compilation files from a previous build, type make clean first_
- This should call avr-gcc, begin compiling grbl, and create a brand new firmware file called grbl.hex that may then be flashed to your Arduino.

#### Install onto Arduino Uno
 
Once you have a compiled .hex file, use [HexUploader app](https://github.com/paulkaplan/HexUploader) to install onto your Arduino Uno. (...this may require some libraries that come with the Arduino IDE software package. If it doesn't work on its own, install Arduino IDE and try again.)
