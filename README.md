To make Clover loader from sources yourself, use my buildme, ebuildme or xbuildme simplified script file updated.

This buildme Much has been updated, absolute paths have been replaced with relative ones. Now Clover can be compiled from any user folder.

Added loading of utilities to the download folder instead of the desktop. Replaced the no longer available PlistEDPlus replaced by Xplist Open source.

Reworked interface color selection elements. Much that was unnecessary was dropped. What I think is necessary has been added.

xbuildme is very old but still a working version which added support for GCC151.

To use these scripts:
1. Open the terminal, enter the commands:
2. cd to the folder where you want to clone the Clover git repository except system ones.
3. git clone --recurse-submodules https://github.com/CloverHackyColor/CloverBootloader.git
5. === Download and install Python 3.12 or higher===.
6. cd /Library/Frameworks/Python.framework/Versions/3.12/bin/
7. === Set a link for python ===
8. sudo ln -s python3.12 python
9. === Install tools ===
10. pip3 install setuptools
11. === cd to the root of the Clover folder ===
12. make -C BaseTools "BUILD_CC=clang"
13. git clone https://github.com/YBronst/CloverBuildScripts.git
14. chmod +x CloverBuildScripts/buildme or chmod +x CloverBuildScripts/xbuildme
15. xattr -d com.apple.quarantine CloverBuildScripts/buildme or xattr -d com.apple.quarantine CloverBuildScripts/xbuildme
16. cp -f CloverBuildScripts/buildme CloverBootloader or cp -f CloverBuildScripts/xbuildme CloverBootloader
17. cd CloverBootloader
18. ./buildme or ./xbuildme 😉
19. Enjoy.
