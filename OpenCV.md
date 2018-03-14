### Download

     https://www.opencv.org/releases.html
  
### Install [Brew](https://github.com/gustavkkk/frequently-used-cmds/blob/master/HomeBrew.md) and [CMake]()

     
### Building

   [Fatal error: 'QTKit/QTKit.h' file not found](https://stackoverflow.com/questions/39735485/opencv-installation-failure-due-to-qtkit) is caused because QTKit has been deprecated in 10.9. [This Report](https://www.pyimagesearch.com/2016/11/28/macos-install-opencv-3-and-python-2-7/) explains above opencv3.2 has solution for this. You can solve this problem to copy QTKIT framework or QuickTime Framework to /System/Library/Frameworks.
     
     $ tar -xvf MacOSX10.11.sdk.tar.xz
     $ cd MacOSX10.12.sdk/System/Library/Frameworks
     [$ sudo cp -rf QTKit.framework /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/System/Library/Frameworks/]
     [$ sudo cp -rf /System/Library/Frameworks]
     $ cd QTKit.framework/Versions/A/Headers
     
   [](https://stackoverflow.com/questions/39590741/fatal-error-qtkit-qtkit-h-file-not-found-when-i-build-opencv-on-mac)
   Here is a workaround solution to fix the issue:
   Download MACOSX SDK here.
   extract head files from MacOSX10.11.sdk/MacOSX10.11.sdk/System/Library/Frameworks/QTKit.framework/Headers/
   Create a folder under opencv source file folder: opencv-3.2.0/modules/highgui/src/QTKit, and copy all header files into the folder.
   Follow the regular opencv build steps. When you run make -j8, you don't need set "-DWITH_QUICKTIME=OFF -DWITH_GSTREAMER=OFF -DWITH_FFMPEG=OFF"
This works for opencv2.x and 3.x

     $ cd opencv-2.4.9
     $ mkdir build
     $
     $ cp -rf *.
     $ cd build
     $ cmake -DWITH_QUICKTIME=OFF -DWITH_GSTREAMER=OFF -DWITH_FFMPEG=OFF -DCMAKE_C_COMPILER=/usr/bin/clang -DCMAKE_CXX_COMPILER=/usr/bin/clang++ -DCMAKE_BUILD_TYPE=Release .. ; make -j4
     [$ cmake -G "Unix Makefiles" ..; make -j8; sudo make install]


