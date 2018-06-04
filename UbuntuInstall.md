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
