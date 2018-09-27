# Ubutu Installation Guide 

### Ubuntu-server 16.04 기준
Kernel 16.04.x -> 최신
```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt dist-upgrade
```
Install 32bit packages 
```
$ sudo dpkg --add-architecture i386
$ sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386
```
### vi font 
```
$ sudo cp molokai.vim  /usr/share/vim/vim74/colors/
$ vi /etc/vim/vimrc (add line: colorscheme "xxx")
>> vim edit :colorscheme elflord
```
### python upgrade (->3.6)
```
$ sudo add-apt-repository ppa:jonathonf/python-3.6; sudo apt-get update
$ sudo apt-get install python3.6
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.5 1
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.6 2
$ sudo update-alternatives --config python3
```
### pip 옵션
```
$ pip search 패키지 
$ pip install 패키지==버전 (예: pip install requests==2.9.0)
$ pip list 또는 pip freeze
$ pip install -Iv http://url/
$ pip install -r requirements.txt
```

### 개발 환경 설치 (예상)
```
sudo apt-get install python-dev python3-dev python3-pip python-pip 
sudo apt-get install make  gcc gcc-multilib cmake
sudo apt-get install build-essential dkms pkg-config libcupti-dev
sudo apt-get install libopenblas-dev libatlas-base-dev gfortran
```

### CUDA / NVIDIA Driver / cuDNN 
```
1. CUDA (버전 8.0RC) 회원 가입 필수
  $ sudo sh cuda_8.0.61_375.26_linux-run (--silent –override) 
2. nvidia 홈페이지 다운로드 
  $ chmod +x NVIDIA-Linux-x86_64-384.98.run
  $ sudo NVIDIA-Linux-x86_64-384.98.run
3. cuDNN 6.0 설치 (cudnn-8.0-linux-x64-v6.0.tgz)
  $ cd cuda; 
  $ sudo cp lib64/libcu* /usr/local/cuda/lib64/
  $ sudo cp include/cudnn.h /usr/local/cuda/include/
4. .bashrc 설정 및 확인
  $ nvcc -V; nvidia-smi
```
```
5. CUDA 8.0 삭제  
  $ sudo apt-get --purge remove 'cuda*'
  $ sudo apt-get autoremove --purge 'cuda*'
6. CUDA 9.0 설치 (CUDA Toolkit 9.0 Downloads)
  $ sudo dpkg -i cuda-repo-ubuntu1604-9-0-local_9.0.176-1_amd64.deb
  $ sudo apt-key add /var/cuda-repo-9-0-local/7fa2af80.pub
  $ sudo apt-get update
  $ sudo apt-get install cuda-9-0
7. CUDA patch 설치 (Patch 1 (Released Jan 25, 2018), ... Patch 4)
  $ sudo dpkg -i cuda-repo-ubuntu1604-9-0-local-cublas-performance-update_1.0-1_amd64-deb
  $ sudo apt-get update; sudo apt-get upgrade cuda-9-0
  $ sudo dpkg -i cuda-repo-ubuntu1604-9-0-local-cublas-performance-update-2_1.0-1_amd64-deb
  $ sudo apt-get update; sudo apt-get upgrade cuda-9-0
  $ sudo dpkg -i cuda-repo-ubuntu1604-9-0-local-cublas-performance-update-3_1.0-1_amd64-deb
  $ sudo apt-get update; sudo apt-get upgrade cuda-9-0
  $ sudo dpkg -i cuda-repo-ubuntu1604-9-0-176-local-patch-4_1.0-1_amd64-deb
  $ sudo apt-get update; sudo apt-get upgrade cuda-9-0
8. cuDNN 7 설치 (Download cuDNN v7.3.0 (Sept 19, 2018), for CUDA 9.0)
  $ tar xvfz cudnn-9.0-linux-x64-v7.3.0.29.solitairetheme8 (cuDNN v7.3.0 Library for Linux)
  $ sudo cp -P cuda/include/cudnn.h /usr/local/cuda/include 
  $ sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda/lib64 
  $ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
  
  $ sudo apt-get install libcupti-dev
9. 환경변수 설정
  $ vi ~/.bashrc 
    export PATH=/usr/local/cuda/bin:$PATH 
    export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:" 
    export CUDA_HOME=/usr/local/cuda
  $ nvcc --version
```
