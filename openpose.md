
# Openpose installation from source (Ubuntu 18.04)
## Install build tools
CMake >= 3.12

gcc, g++ >= 7.4.0

[CUDA 10.1]([https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=deblocal](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=deblocal))

[cuDNN 7.6 runtime](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v7.6.1.34/prod/10.1_20190620/Ubuntu18_04-x64/libcudnn7_7.6.1.34-1%2Bcuda10.1_amd64.deb)

[cuDNN 7.6 dev](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v7.6.1.34/prod/10.1_20190620/Ubuntu18_04-x64/libcudnn7-dev_7.6.1.34-1%2Bcuda10.1_amd64.deb)

Install the following packages by **apt-get install** for opencv

1. libgtk2.0-dev 

2. pkg-config

3. libcanberra-gtk-module

Git clone vcpkg from [GitHub]([https://github.com/microsoft/vcpkg](https://github.com/microsoft/vcpkg)) and build by the provided **./bootstrap-vcpkg.sh**

Install essential packages by **vcpkg install**:
1. opencv
2. protobuf
3. boost
4. hdf5[cpp]
5. openblas

Install the following packages by **apt-get install**
libgoogle-glog-dev


## Build caffe from source
Git Clone the repository
[Nvidia Caffe](https://github.com/NVIDIA/caffe.git)
> mkdir -p build && cd build
> cmake -DCMAKE_TOOLCHAIN_FILE=../../vcpkg/scripts/buildsystems/vcpkg.cmake -DBUILD_python=OFF -DUSE_LMDB=OFF -DUSE_LEVELDB=OFF ..
> cmake -DCMAKE_INSTALL_PREFIX=${HOME}/3rd/nv_caffe --build . --config Release --target install -- -j 10


settings.json for reference
``` json
{

"cmake.configureArgs": [
"-DCMAKE_TOOLCHAIN_FILE=${workspaceRoot}/../vcpkg/scripts/buildsystems/vcpkg.cmake",
"-DBUILD_python=OFF",
"-DUSE_LMDB=OFF",
"-DUSE_LEVELDB=OFF"
],

"cmake.preferredGenerators": [
"Unix Makefiles",
"Ninja"
],

"C_Cpp.default.configurationProvider": "vector-of-bool.cmake-tools",

"cmake.configureOnOpen": true,

"cmake.buildDirectory": "${workspaceRoot}/build/${buildType}",

}
```

After the build process success, the install folder will be appear in the build folder. 

## Build openpose
Install the following packages by **apt-get install** for opencv

1. libgtk2.0-dev 

2. pkg-config

3. libcanberra-gtk-module

Git Clone the repository

[openpose]([https://github.com/CMU-Perceptual-Computing-Lab/openpose](https://github.com/CMU-Perceptual-Computing-Lab/openpose))

> cmake -G"Unix Makefiles" -DCMAKE_TOOLCHAIN_FILE=${workspaceRoot}/../vcpkg/scripts/buildsystems/vcpkg.cmake -DDL_FRAMEWORK=NV_CAFFE -DBUILD_CAFFE=OFF -DCaffe_INCLUDE_DIRS=$HOME/git/vcpkg/installed/x64-linux/include;/usr/include;$HOME/git/nv_caffe/build/Release/include;/usr/local/cuda/include;$HOME/git/vcpkg/installed/x64-linux/include/opencv;$HOME/git/vcpkg/installed/x64-linux/include/openblas;${workspaceRoot}/../nv_caffe/build/Release/install/include -DCaffe_LIBS=${workspaceRoot}/../nv_caffe/build/Release/install/lib/libcaffe-nv.so ..

settings.json for reference
``` json
{

"cmake.configureArgs": [
"-DCMAKE_TOOLCHAIN_FILE=${workspaceRoot}/../vcpkg/scripts/buildsystems/vcpkg.cmake",
"-DDL_FRAMEWORK=NV_CAFFE",
"-DBUILD_CAFFE=OFF",
"-DCaffe_INCLUDE_DIRS=${env:HOME}/git/vcpkg/installed/x64-linux/include;/usr/include;${env:HOME}/git/nv_caffe/build/Release/include;/usr/local/cuda/include;${env:HOME}/git/vcpkg/installed/x64-linux/include/opencv;${env:HOME}/git/vcpkg/installed/x64-linux/include/openblas;${workspaceRoot}/../nv_caffe/build/Release/install/include",
"-DCaffe_LIBS=${workspaceRoot}/../nv_caffe/build/Release/install/lib/libcaffe-nv.so"
],

"cmake.preferredGenerators": [
"Unix Makefiles",
"Ninja"
],

"C_Cpp.default.configurationProvider": "vector-of-bool.cmake-tools",

"cmake.configureOnOpen": true,

"cmake.buildDirectory": "${workspaceRoot}/build/${buildType}",

}
```

---
> Written by Alex Choi <choiip@gmail.com> with [StackEdit](https://stackedit.io/).