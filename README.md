To build a Clover bootloader from source on your own, use my updated extended buildme script, or the old but updated xbuildme script.
In this buildme, many things have been updated, absolute paths have been replaced with relative ones. Now Clover can be compiled from any user folder, except system or write-protected ones.
Utilities are now downloaded to the Downloads folder instead of the Desktop. The outdated PlistEDPlus has been replaced with Xplist, which is open source.
Interface color selection elements have been redesigned. Much of the unnecessary stuff has been removed, and things I consider necessary have been added.
To use these scripts:
=== Open Terminal and enter the following commands in order ===
cd "folder_name" (the folder where you want to clone the Clover git repository, excluding system folders).
git clone --recurse-submodules https://github.com/CloverHackyColor/CloverBootloader.git
=== Download and install Python 3.12 or higher and go to its installation folder. ===
cd /Library/Frameworks/Python.framework/Versions/3.12/bin/
=== Create an alias for Python. ===
sudo ln -s python3.12 python
=== Install the tools. ===
pip3 install setuptools
=== Go to the root folder of Clover. ===
cd "folder_name"
make -C BaseTools "BUILD_CC=clang"
=== Go back one level ===
cd ..
=== Download the build scripts ===
git clone https://github.com/YBronst/CloverBuildScripts.git
=== If necessary, set them as executable ===
chmod +x CloverBuildScripts/buildme or chmod +x CloverBuildScripts/xbuildme
=== Remove quarantine attribute. ===
xattr -d com.apple.quarantine CloverBuildScripts/buildme or xattr -d com.apple.quarantine CloverBuildScripts/xbuildme
=== Copy them (with replacement) into the Clover folder. ===
cp -f CloverBuildScripts/buildme CloverBootloader or cp -f CloverBuildScripts/xbuildme CloverBootloader
=== Go to the root folder of Clover. ===
cd CloverBootloader
./buildme or ./xbuildme 😉
Enjoy watching the compilation process!
