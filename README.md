To make Clover loader from sources yourself, use my buildme, ebuildme or xbuildme simplified script file updated.

This buildme and ebuildme Much has been updated, absolute paths have been replaced with relative ones. Now Clover can be compiled from any user folder.

Added loading of utilities to the download folder instead of the desktop. Replaced the no longer available PlistEDPlus replaced by Xplist Open source.

Reworked interface color selection elements. Much that was unnecessary was dropped. What I think is necessary has been added.

ebuildme the same as buildme but only english.

xbuildme is very old but still a working version which added support for GCC151.
To use these scripts:
1. Open the terminal, enter the commands:
2. cd src
3. git clone https://github.com/YBronst/CloverBuildScripts.git
4. chmod +x CloverBuildScripts/buildme && chmod +x CloverBuildScripts/ebuildme && chmod +x CloverBuildScripts/xbuildme
5. cp -f CloverBuildScripts/buildme CloverBootloader && cp -f CloverBuildScripts/ebuildme CloverBootloader && cp -f CloverBuildScripts/xbuildme CloverBootloader
6. cd CloverBootloader
7. ./buildme (./ebuildme) or ./xbuildme 😉
