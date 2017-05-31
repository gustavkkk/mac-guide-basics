# mac-guide-basics
macos
# check system info
  sysctl -a machdep.cpu
# python
1. install opencv(http://www.pyimagesearch.com/2016/12/05/macos-install-opencv-3-and-python-3-5/)

        $ cmake -D CMAKE_BUILD_TYPE=RELEASE \
          -D CMAKE_INSTALL_PREFIX=/usr/local \
          -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules \
          -D PYTHON3_LIBRARY=/usr/local/Cellar/python3/3.5.2_3/Frameworks/Python.framework/Versions/3.5/lib/python3.5/config-3.5m/libpython3.5.dylib \
          -D PYTHON3_INCLUDE_DIR=/usr/local/Cellar/python3/3.5.2_3/Frameworks/Python.framework/Versions/3.5/include/python3.5m/ \
          -D PYTHON3_EXECUTABLE=$VIRTUAL_ENV/bin/python \
          -D BUILD_opencv_python2=OFF \
          -D BUILD_opencv_python3=ON \
          -D INSTALL_PYTHON_EXAMPLES=ON \
          -D INSTALL_C_EXAMPLES=OFF \
          -D BUILD_EXAMPLES=ON ..
                 
2. install dlib
