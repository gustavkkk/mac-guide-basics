# MAC-BEGINNER-GUIDE

  My Favorites/My Found in MacOS
  
# COMMANDS 

  ### check system info
    
    sysctl -a machdep.cpu

  ### brew install opencv
  
    brew install gcc --force-bottle
    brew reinstall gcc --without-multilib
    brew tap homebrew/science
    brew install opencv --32-bit
    
# INSTALLATION

### [BREW INSTALL](https://coolestguidesontheplanet.com/installing-homebrew-on-macos-sierra-package-manager-for-unix-apps/)

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  
### Qt INSTALL
  
    http://download.qt.io/official_releases/qt/
    
    http://ftp.jaist.ac.jp/pub/qtproject/online/qt5/mac/x64/online_repository/
        
  
### PYTHON IDE

   Install anaconda + opencv(https://stackoverflow.com/questions/41873941/cant-install-opencv3-on-anaconda3-python3-6-on-macos)

        # all versions
        https://www.continuum.io/downloads
        https://docs.continuum.io/anaconda/#previous-versions
        https://docs.continuum.io/anaconda/oldpkglists
        https://repo.continuum.io/archive/
        I recommend you that anaconda4.2.0 should be installed.
        # guide
        you make sure the installation location is /root
        while installing, it will need you to type admin pw
        $which python3
        /anaconda/bin/python3
        $cat ~/.bash_profile
        (# added by Anaconda3 4.3.1 installer
        export PATH="/anaconda/bin:$PATH")
        $conda list
        (you can see the packages)
        #check python version which support opencv
        https://anaconda.org/menpo/opencv3/files
        #downgrade python
        $conda install python=3.5
        # install opencv
        https://github.com/conda-forge/opencv-feedstock
        $conda install numpy
        $conda config --add channels conda-forge
        $conda install opencv

   install python + opencv(http://www.pyimagesearch.com/2016/12/05/macos-install-opencv-3-and-python-3-5/)

        $brew install python3
        $brew install numpy
        $which python3
        /usr/local/bin
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
          
   install dlib

        $sudo pip install dlib
        
