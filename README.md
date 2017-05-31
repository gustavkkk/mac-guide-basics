# mac-guide-basics
macos
# check system info
  sysctl -a machdep.cpu
# python
1. Install anaconda([https://www.continuum.io/downloads])

2. install opencv(http://www.pyimagesearch.com/2016/12/05/macos-install-opencv-3-and-python-3-5/)

        -python 3.5.2
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
        
        -python 3.6.1
        $ cmake -D CMAKE_BUILD_TYPE=RELEASE \
          -D PYTHON3_EXECUTABLE=$(which python3) \
          -D PYTHON3_INCLUDE_DIR=$(python3 -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") \
          -D PYTHON3_LIBRARY=/usr/local/Cellar/python3/3.6.1/Frameworks/Python.framework/Versions/3.6/lib/python3.6/config-3.6m-darwin/libpython3.6.dylib \
          -D PYTHON3_LIBRARIES=/usr/local/Cellar/python3/3.6.1/Frameworks/Python.framework/Versions/3.6/bin \
          -D PYTHON3_INCLUDE_DIR=/usr/local/Cellar/python3/3.6.1/Frameworks/Python.framework/Versions/3.6/Headers \
          -D PYTHON3_PACKAGES_PATH=$(python3 -c "from distutils.sysconfig import get_python_lib; print(get_python_lib())") \
          -D BUILD_opencv_python2=OFF \
          -D BUILD_opencv_python3=ON \
          -D INSTALL_C_EXAMPLES=OFF -D INSTALL_PYTHON_EXAMPLES=ON \
          -D BUILD_EXAMPLES=ON \
          -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules ..
          
3. install dlib

        $sudo pip install dlib
        
4. Usage of conda[https://stackoverflow.com/questions/41873941/cant-install-opencv3-on-anaconda3-python3-6-on-macos]

        - Usage of virtual environment    
        $conda list | grep python
        $conda create -yn opencvtest python=3.5.2
        $source activate opencvtest
        $conda list | grep python
        $conda search -c conda-forge --spec 'opencv=3*'
        $conda install -y -c conda-forge opencv
        $conda list | grep -e python -e opencv
        
        - Upgrade and Downgrade of anaconda, Direct Installation of OpenCV
        $conda install python=3.5
        $conda install -c menpo opencv3
