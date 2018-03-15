### 1. dyld: Symbol not found: __cg_jpeg_resync_to_restart
###     Referenced from: /System/Library/Frameworks/ImageIO.framework/Versions/A/ImageIO
###     Expected in: /usr/local/lib/libJPEG.dylib
###     in /System/Library/Frameworks/ImageIO.framework/Versions/A/ImageIO
    
    $ sudo cp -f /System/Library/Frameworks/ImageIO.framework/Versions/A/Resources/libJPEG.dylib /usr/local/lib/libJPEG.dylib
    $ sudo cp -f /System/Library/Frameworks/ImageIO.framework/Versions/A/Resources/libTIFF.dylib /usr/local/lib/libTIFF.dylib

### 2. ld: symbol(s) not found for architecture x86_64 
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

### 3.Operation not permitted

    System Integrity Protection
