### - dyld: Symbol not found: __cg_jpeg_resync_to_restart
### Referenced from: /System/Library/Frameworks/ImageIO.framework/Versions/A/ImageIO
###     Expected in: /usr/local/lib/libJPEG.dylib
###     in /System/Library/Frameworks/ImageIO.framework/Versions/A/ImageIO
    
    $ sudo cp -f /System/Library/Frameworks/ImageIO.framework/Versions/A/Resources/libJPEG.dylib /usr/local/lib/libJPEG.dylib
    $ sudo cp -f /System/Library/Frameworks/ImageIO.framework/Versions/A/Resources/libTIFF.dylib /usr/local/lib/libTIFF.dylib

### - ld: symbol(s) not found for architecture x86_64 
###   clang: error: linker command failed with exit code 1 (use -v to see invocation)

   opencv
   
    $ cp /usr/local/share/OpenCV/3rdparty/lib/libippicv.a /usr/local/lib/
    $ cd /usr/local/lib
    $ chmod a+x libippicv.a
    $ export DYLD_LIBRARY_PATH=$DYLD_LIBRARY_PATH:/usr/local/lib
    
   qt
   
    1. Install
    2. Set Env
    $ export PATH=$PATH:/Users/'whoami'/Qt5.10.0/5.10.0/clang_64/bin

### - [Operation not permitted](https://stackoverflow.com/questions/32659348/operation-not-permitted-when-on-root-el-capitan-rootless-disabled)

    System Integrity Protection
    Nvm. For anyone else having this problem you need to reboot your mac and press ⌘+R when booting up. Then go into Utilities > Terminal and type the following commands:
    $ csrutil disable
    $ reboot 
    
### - [Fatal error: 'QTKit/QTKit.h' file not found](https://stackoverflow.com/questions/39590741/fatal-error-qtkit-qtkit-h-file-not-found-when-i-build-opencv-on-mac)

     $ tar -xvf MacOSX10.11.sdk.tar.xz
     $ cd opencv-2.4.9
     $ mkdir build
     $ cd modules/highgui/src
     $ mkdir QTKit
     $ cp -rf ~/MacOSX10.12.sdk/System/Library/Frameworks/QTKit.framework/Versions/A/Headers/*.* QTKit/
     $ cd ~/opencv-2.4.9/build
     $ cmake -DWITH_QUICKTIME=OFF -DWITH_GSTREAMER=OFF -DWITH_FFMPEG=OFF -DCMAKE_C_COMPILER=/usr/bin/clang -DCMAKE_CXX_COMPILER=/usr/bin/clang++ -DCMAKE_BUILD_TYPE=Release .. ; make -j4
     $ sudo make install
     
### [Macdeployqt - Error: no file in /usr/lib/libfsdk.dylib](https://stackoverflow.com/questions/2809930/macdeployqt-and-third-party-libraries)

    1. Run macdeployqt to enjoy its useful but feebly inadequate benefits
    $ macdeployqt <path_to_your_nascent_app_bundle>/foo.app
    2. Install your extra libraries manually
    $ cp <original_library_path> foo.app/Contents/Frameworks/<lib_name>
    3. Find out what libraries each binary links to.
    otool -L <binary_file_name>
    Change the internal libary paths in your binaries
    4. install_name_tool -change <original_library_path> @executable_path/../Frameworks/<lib_name> <binary_file_name>

