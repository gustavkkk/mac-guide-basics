### Download

     https://www.opencv.org/releases.html
  
### Install [Brew](https://github.com/gustavkkk/frequently-used-cmds/blob/master/HomeBrew.md) and [CMake]()

     
### Building

   Problem:[fatal error: 'QTKit/QTKit.h' file not found](https://stackoverflow.com/questions/39735485/opencv-installation-failure-due-to-qtkit) caused by the fact that QTKit has been deprecated in 10.9. [This Report](https://www.pyimagesearch.com/2016/11/28/macos-install-opencv-3-and-python-2-7/) explains above opencv3.2 has solution for this.
   
     $ cd opencv-2.4.9
     $ mkdir build
     $ cd build
     $ cmake -DWITH_QUICKTIME=OFF -DWITH_GSTREAMER=OFF -DWITH_FFMPEG=OFF -DCMAKE_C_COMPILER=/usr/bin/clang -DCMAKE_CXX_COMPILER=/usr/bin/clang++ -DCMAKE_BUILD_TYPE=Release .. ; make -j4
     [$ cmake -G "Unix Makefiles" ..; make -j8; sudo make install]


