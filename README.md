# Clover Bootloader Build Instructions

To build a Clover bootloader from source, you can use either my **updated extended `buildme` script** or the older but updated `xbuildme` script.

### Updates in this `buildme`:

* Absolute paths replaced with relative ones.
* Can now compile Clover from any user folder (except system or write-protected folders).
* Utilities are downloaded to the **Downloads** folder instead of the Desktop.
* Outdated **PlistEDPlus** replaced with **Xplist** (open source).
* Interface color selection elements redesigned.
* Removed unnecessary components; added essential ones.

## Step-by-Step Instructions

### 1. Open Terminal and clone Clover repository

```bash
cd "folder_name"  # choose your folder, avoid system folders
git clone --recurse-submodules https://github.com/CloverHackyColor/CloverBootloader.git
```

### 2. Install Python 3.12 or higher

```bash
# Navigate to Python installation folder
cd /Library/Frameworks/Python.framework/Versions/3.12/bin/

# Create an alias for Python
sudo ln -s python3.12 python
```

### 3. Install necessary Python tools

```bash
pip3 install setuptools
```

### 4. Build BaseTools for Clover

```bash
cd "folder_name"  # root folder of Clover
make -C BaseTools BUILD_CC=clang
```

### 5. Prepare the build scripts

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

# Copy scripts to Clover folder (overwrite if needed)
cp -f CloverBuildScripts/buildme CloverBootloader
cp -f CloverBuildScripts/xbuildme CloverBootloader
```

### 6. Build Clover

```bash
cd CloverBootloader
./buildme  # or ./xbuildme 😉
```

Enjoy watching the compilation process!
