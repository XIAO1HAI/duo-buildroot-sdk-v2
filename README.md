# Milk-V Duo series buildroot SDK V2

1、基于milkvtech/milkv-duo的duodocker镜像【推荐第一种方法】
运行docker
```
docker run -itd --name duodocker -v $(pwd):/home/work milkvtech/milkv-duo:latest /bin/bash
```
链接python3.xx到python(以此docker为例，默认自带python3.10)
```
ln -s /usr/bin/python3.10 /usr/bin/python
```
此步之后可以跳过第2步，直接进行第3步

2、安装相关依赖包（基于sophg/tpuc_dev的docker情况下）
安装sophgo/tpuc_dev docker
```
docker run -v $PWD/..:/workspace -p 8001:8001 -it --name myname sophgo/tpuc_dev:v3.1
```
安装依赖
```
apt-get update
apt-get install bison flex aptitude bc rsync device-tree-compiler pkg-config expect 
aptitude install libssl-dev
```
3、编译buildroot
```
./build.sh lunch
```
