# CloverBuildScripts
README.md
# Clover bootloader build instructions

# To build the Clover bootloader from source, you can use either any any of my **updated `buildme` scripts**
- slice-buildme - #original
- cduldme - #clean version #built-in update - works, but nothing compiles after it. Solved by running pbuildme once
- pbuildme - #version with built-in patches - raw
- xbuildme - #vintage
- Clover Builder Clean - Download Clover source code and patch them and download release version buildme 

### Updates in this `buildme`:

* Absolute paths have been replaced with relative ones.
* Now you can compile Clover from any user folder (except for the system and write-protected ones).
* Reworked interface color picker elements.
* Removed unnecessary components, such as utilities.
* Links quickly become outdated and you can download them manually.

## Step-by-step instructions

### 1. Open Terminal and clone the Clover repository

```bash
cd "folder_name" # select the desired folder, avoiding system folders (as usual source)
git clone --recurse-submodules https://github.com/CloverHackyColor/CloverBootloader.git
```

### 2. Install Python 3.13.7

```bash
# Go to the Python installation folder
cd /Library/Frameworks/Python.framework/Versions/3.13/bin/

# Create an alias for Python
sudo ln -s python3.13 python
```

### 3. Install the necessary Python tools

```bash
pip3 install setuptools
```
### 4. Update the necessary Python tools
```bash
pip3 install update
```

### 5. Build BaseTools for Clover

```bash
cd CloverBootloader
make -C BaseTools BUILD_CC=clang
```

### 6. Preparing build scripts

```bash
# Go back one level
cd ..

# Download build scripts
git clone https://github.com/YBronst/CloverBuildScripts.git

# Make scripts executable (if necessary)
chmod +x CloverBuildScripts/buildme
chmod +x CloverBuildScripts/*buildme

# Remove quarantine attribute
xattr -rc CloverBuildScripts/buildme
xattr -rc CloverBuildScripts/*buildme

# Copy scripts to Clover folder (overwrite if necessary)
cp -f CloverBuildScripts/buildme CloverBootloader
cp -f CloverBuildScripts/xbuildme CloverBootloader
```

### 7. Building Clover

```bash
cd CloverBootloader
./buildme # or ./xbuildme 😉
```

Enjoy watching the compilation process!

