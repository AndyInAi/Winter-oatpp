# Winter-oatpp

```sh

echo "
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse
" > /etc/apt/sources.list

export DEBIAN_FRONTEND=noninteractive

apt update -y

apt install -y git cmake build-essential

if [ ! -d ~/Winter-oatpp ]; then cd ~/ ; git clone https://github.com/AndyInAi/Winter-oatpp.git; fi


# 运行

cd  ~/Winter-oatpp

chmod +x ./Winter-oatpp

./Winter-oatpp

# starting HTTP server at http://0.0.0.0:8080/


# 或者安装编译环境，编译源代码后运行

cd ~/ && git clone https://github.com/oatpp/oatpp.git

mkdir -p ~/oatpp/build/oatlib

cd ~/oatpp/build && cmake -DOATPP_BUILD_TESTS=OFF -DCMAKE_BUILD_TYPE=Release ..

# cd ~/oatpp/build && make -j $(nproc) install DESTDIR=./oatlib
cd ~/oatpp/build && make -j $(nproc) install


# 编译源代码

mkdir -p ~/Winter-oatpp/build

cd ~/Winter-oatpp/build && cmake .. && make -j $(nproc)

# 运行

~/Winter-oatpp/build/Winter-oatpp

# starting HTTP server at http://0.0.0.0:8080/

```
