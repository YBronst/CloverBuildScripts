To make Clover loader from sources yourself, use my buildme, ebuildme or xbuildme simplified script file updated.

This buildme Much has been updated, absolute paths have been replaced with relative ones. Now Clover can be compiled from any user folder.

Added loading of utilities to the download folder instead of the desktop. Replaced the no longer available PlistEDPlus replaced by Xplist Open source.

Reworked interface color selection elements. Much that was unnecessary was dropped. What I think is necessary has been added.

xbuildme is very old but still a working version which added support for GCC151.

To use these scripts:
1. === Open the terminal, enter the following commands ===
2. cd "folder name" (Where the folder where you want to clone the Clover git repository except system ones).
3. git clone --recurse-submodules https://github.com/CloverHackyColor/CloverBootloader.git
5. === Download and install Python 3.12 or higher===.
6. cd /Library/Frameworks/Python.framework/Versions/3.12/bin/
7. === Set a link for python ===
8. sudo ln -s python3.12 python
9. === Install tools ===
10. pip3 install setuptools
11. === Go to the root of the Clover folder ===
12. cd "folder name"
13. make -C BaseTools "BUILD_CC=clang"
14. === Go back ===
15. cd ..
16. === Download compilation scripts ===
17. git clone https://github.com/YBronst/CloverBuildScripts.git
18. === If necessary, set the flag for execution ===
19. chmod +x CloverBuildScripts/buildme or chmod +x CloverBuildScripts/xbuildme
20. === Exclude them from quarantine ===
21. xattr -d com.apple.quarantine CloverBuildScripts/buildme or xattr -d com.apple.quarantine CloverBuildScripts/xbuildme
22. === Copy them to the Clover folder ===
23. cp -f CloverBuildScripts/buildme CloverBootloader or cp -f CloverBuildScripts/xbuildme CloverBootloader
24. === Go to the root folder of Clover ===
25. cd CloverBootloader
26. ./buildme or ./xbuildme 😉
27. Enjoy.
