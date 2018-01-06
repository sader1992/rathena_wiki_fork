This guide covers the process of adding Custom Monsters to your Server and Client and also, all related elements to make the new entry as close as possible of the official content.

# Client-Side

## Sound Effects (SFX)
If your monster holds any special sound effects, not original from the default library, note that to be played properly by the client it must: 
* Generated, rercorded or converted to WAV.
* Be set in a bit rate no superior than 352kbps.

The safest way found to achieve perfect use of the SFX by the client is converting any file using [Audacity](http://www.audacityteam.org/download/) or similar audio editors. Converting the file on popular all-media converters, such as [Format Factory](https://formatfactory.en.uptodown.com/windows) at default settings will result in a high bit rate, and although it can be played normally by other software, the client is uncompatible with it.

For uncompressed formats, such as WAV, the bit-rate (number of binary digits per second) can be calculated from the "sample rate", "sample format" and "number of audio channels".

### Converting on Audacity
* Open or Import desired audio file (such as OGG).
* Select 'Export As' on 'File' menu and save it as WAV.
* Right-click the exported file, check the 'Details' tab bit rate, if it's not above 352 kbps it should work.

### Converting on FormatFactory
* Import or drag the desired audio file to the window.
* Select 'Audio' then 'WAV' and, before clicking 'Ok', hit 'Settings'.
* Change 'Sample Rate' to 11025 and set 'Audio Channel' to 2, hit 'Ok' and click 'Start'.
* Right-click the exported file, check the 'Details' tab bit rate, if it's not above 352 kbps it should work.