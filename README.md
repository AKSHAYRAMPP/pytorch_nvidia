# pytorch_nvidia
Installation method of pytorch on nvidia Jetson. 

Tested board: Nvidia Xavier AGX, Nvidia Jetson TX2

Jetpack version: Jetpack 4.6.2

## Steps:

1. Install system packages required by PyTorch:

 ```cmd
 
  sudo apt-get -y update
  
  sudo apt-get -y install autoconf bc build-essential g++-8 gcc-8 clang-8 lld-8 gettext-base gfortran-8 iputils-ping libbz2-dev libc++-dev libcgal-dev libffi-dev libfreetype6-dev libhdf5-dev libjpeg-dev liblzma-dev libncurses5-dev libncursesw5-dev libpng-dev libreadline-dev libssl-dev libsqlite3-dev libxml2-dev libxslt-dev locales moreutils openssl python-openssl rsync scons python3-pip libopenblas-dev
  
  ```
  
2. Download the [wheel file](https://drive.google.com/file/d/1pSJpaCM8GYNvxxzFse92OKOWEhLH8-pb/view?usp=share_link) and set.

 
 ```cmd
 
 export TORCH_INSTALL=path/to/wheel/file
 
 ```
 
3.Install PyTorch


 ```cmd
 
 python3 -m pip install --upgrade pip

 export "LD_LIBRARY_PATH=/usr/lib/llvm-8/lib:$LD_LIBRARY_PATH"
 
 python3 -m pip install aiohttp numpy=='1.19.4' scipy=='1.5.3'
 
 python3 -m pip install --upgrade protobuf
 
 python3 -m pip install --no-cache $TORCH_INSTALL
 
 ```
 
 4. For testing if pytorch is installed:
     
     
 ```cmd
 
     python3
     
     >>>import torch
     
     >>>print(torch.__version__)
     
```
     
     
   If properly installed, it will display the pytorch version.
