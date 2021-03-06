# Lyli

Lyli (*Ly*tro *Li*nux) aims to provide an open source alternative to the Lytro Desktop.

The application has been tested only with the original Lytro camera, although the Lytro Illum
may work, too.

## Compiling
### Requirements
* c++14 enabled compiler - tested with gcc 4.9
* libusb 1.0
* Qt 5 (Qt5Core, Qt5Widgets) - tested with Qt 5.4, required for GUI
* OpenCV

### Compilation

- Make sure requirements above are satisfied. In Ubuntu, you should be able to run following to install all at once:
```bash
sudo apt-get install gcc libusb-1.0-0-dev libqt5core5a libqt5widgets5 libjsoncpp-dev libopencv-dev
```

- You might need these packages as well:
```bash
sudo apt-get install libtbb-dev hgsvn
```

- Clone this repository, and create a "build" folder.
```
cd ~
git clone https://github.com/hazirbas/lyli.git
cd lyli
mkdir build
cd build
```

- Then build with CMake.
```
cmake ..
make
```

If everything goes well, there should be a *lyli* executable in the build directory and *lyli-qt* in build/ui in case the Qt GUI was compiled.

## Usage
Lyli requires direct access to the USB bus. This can be achieved either by running Lyli as root (not recommended), or by putting the provided `51-lytro.rules` to `/etc/udev/rules.d/` which enables non-root access to the camera.

There are two binaries build:

* _lyli_ - can be found in the top-level build directory, it provides basic command line access to camera

* _lyli-qt_ - GUI application that is build only if the required Qt5 packages are present. Provides most of the features

## License
Most of the Lyli is licensed under LGPL v3, only the Qt GUI (in the ui/ subdirectory)
is licensed under GPL v3.

