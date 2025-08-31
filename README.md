# CloverBuildScripts
README.md
# Clover bootloader build instructions

To build the Clover bootloader from source, you can use either my **updated `buildme` script** or the very old but updated `xbuildme` script.
- There is also `tbuildme`, which is the same `buildme`, but under a different name to protect the original from being overwritten when updating the Clover repository.

### Updates in this `buildme`:

* Absolute paths have been replaced with relative ones.
* Now you can compile Clover from any user folder (except for the system and write-protected ones).
* Reworked interface color picker elements.
* Removed unnecessary components, such as utilities.
* Links quickly become outdated and you can download them manually.

## Step-by-step instructions

### 1. Open Terminal and clone the Clover repository

```bash
cd "folder_name" # select the desired folder, avoiding system folders
git clone --recurse-submodules https://github.com/CloverHackyColor/CloverBootloader.git
```

### 2. Install Python 3.12 or higher

```bash
# Go to the Python installation folder
cd /Library/Frameworks/Python.framework/Versions/3.12/bin/

# Create an alias for Python
sudo ln -s python3.12 python
```

### 3. Install the necessary Python tools

```bash
pip3 install setuptools
```

### 4. Build BaseTools for Clover

```bash
cd "folder_name" # Clover root folder
make -C BaseTools BUILD_CC=clang
```

### 5. Preparing build scripts

```bash
# Go back one level
cd ..

# Download build scripts
git clone https://github.com/YBronst/CloverBuildScripts.git

# Make scripts executable (if necessary)
chmod +x CloverBuildScripts/buildme
chmod +x CloverBuildScripts/xbuildme

# Remove quarantine attribute
xattr -d com.apple.quarantine CloverBuildScripts/buildme
xattr -d com.apple.quarantine CloverBuildScripts/xbuildme

# Copy scripts to Clover folder (overwrite if necessary)
cp -f CloverBuildScripts/buildme CloverBootloader
cp -f CloverBuildScripts/xbuildme CloverBootloader
```

### 6. Building Clover

```bash
cd CloverBootloader
./buildme # or ./xbuildme 😉
```

Enjoy watching the compilation process!

