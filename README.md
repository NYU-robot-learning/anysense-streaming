# A library accompanying the [*AnySense*](https://anysense.app) app. 

**This library is adapted from the [Record3D](https://github.com/marek-simonik/record3d) streaming library.**

## Prerequisites
  - Install [CMake](https://cmake.org/download/) >= **3.13.0** and make sure it is in `PATH`.
  - When on macOS and Windows, install [iTunes](https://www.apple.com/itunes/).
  - When on Linux, install [`libusbmuxd`](https://launchpad.net/ubuntu/+source/libusbmuxd) (`sudo apt install libusbmuxd-dev`). It should be installed by default on Ubuntu.
  
## Installing
The libraries are multiplatform — macOS, Linux and Windows are supported.

### Python
Build from source (run as admin/root):
    
    git clone https://github.com/NYU-robot-learning/anysense-streaming.git
    cd anysense-streaming
    python setup.py install

Note: you may need to run `sudo python setup.py install` to run as root. 
    
### C++
After running the following, you will find compiled static library in the `build` folder and header files in the `include` folder.

**macOS and Linux**

    git clone https://github.com/NYU-robot-learning/anysense-streaming.git
    cd anysense-streaming
    mkdir build && cd build
    cmake -DCMAKE_BUILD_TYPE=Release ..
    make -j8 record3d_cpp
    make install
    # now you can link against the `record3d_cpp` library in your project

**Windows**

    git clone https://github.com/NYU-robot-learning/anysense-streaming.git
    cd anysense-streaming
    md build
    cd build
    cmake -DCMAKE_BUILD_TYPE=Release -G "Visual Studio 15 2017 Win64" ..
    # Open the generated Visual Studio Solution (.sln) fil and build the "`record3d_cpp`" Project

## Sample applications
There is a Python (`demo-main.py`) and C++ (`src/DemoMain.cpp`) sample project that demonstrates how to use the library to receive and display RGBD stream.

Before running the sample applications, connect your iOS device to your computer and open the AnySense iOS app. Go to the Settings tab and enable "USB Streaming mode".

### Python
After installing the modified `record3d` library via the instructions above, run `python demo-main.py` and press the record button to start streaming RGBD data.

### C++
You can build the C++ demo app by running the following (press the record button in the iOS app to start streaming RGBD data):

**macOS and Linux**

    git clone https://github.com/NYU-robot-learning/anysense-streaming.git
    cd anysense-streaming
    mkdir build && cd build
    cmake -DCMAKE_BUILD_TYPE=Release ..
    make -j8 demo
    ./demo
    
**Windows**

    git clone https://github.com/NYU-robot-learning/anysense-streaming.git
    cd anysense-streaming
    md build
    cd build
    cmake -DCMAKE_BUILD_TYPE=Release -G "Visual Studio 15 2017 Win64" ..
    # Open the generated Visual Studio Solution (.sln) file and run the "`demo`" Project
