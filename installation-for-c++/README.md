# Installation for c++

### Step 1 – Updating Ubuntu

```text
$ sudo apt-get update
$ sudo apt-get upgrade
```

### Step 2 – Install dependencies

```text
$ sudo apt-get install build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev 
$ sudo apt-get install python3.5-dev python3-numpy libtbb2 libtbb-dev
$ sudo apt-get install libjpeg-dev libpng-dev libtiff5-dev libjasper-dev libdc1394-22-dev libeigen3-dev libtheora-dev libvorbis-dev libxvidcore-dev libx264-dev sphinx-common libtbb-dev yasm libfaac-dev libopencore-amrnb-dev libopencore-amrwb-dev libopenexr-dev libgstreamer-plugins-base1.0-dev libavutil-dev libavfilter-dev libavresample-dev
```

### Step 3 –  Get OpenCV

```text
$ sudo -s
$ cd /opt
/opt$ git clone https://github.com/Itseez/opencv.git
/opt$ git clone https://github.com/Itseez/opencv_contrib.git
```

### Step 4 – build and install OpenCV

```text
/opt$ cd opencv
 
/opt/opencv$ mkdir release
 
/opt/opencv$ cd release
 
/opt/opencv/release$ cmake -D BUILD_TIFF=ON -D WITH_CUDA=OFF -D ENABLE_AVX=OFF -D WITH_OPENGL=OFF -D WITH_OPENCL=OFF -D WITH_IPP=OFF -D WITH_TBB=ON -D BUILD_TBB=ON -D WITH_EIGEN=OFF -D WITH_V4L=OFF -D WITH_VTK=OFF -D BUILD_TESTS=OFF -D BUILD_PERF_TESTS=OFF -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=/opt/opencv_contrib/modules /opt/opencv/
 
/opt/opencv/release$ make -j4
 
/opt/opencv/release$ make install
 
/opt/opencv/release$ ldconfig
 
/opt/opencv/release$ exit
 
/opt/opencv/release$ cd ~
```

**Now to check if OpenCV is installed on a machine, run the following commands**

```text
$ pkg-config --modversion opencv
3.2.x
```

We will get the opencv version installed in this case it’s 3.2.x



