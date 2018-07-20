## Build From Source code
**Note**: Git clone this repertory in your '$HOME' 
```sh
cd $HOME

git clone https://github.com/Agzs/zkp-sc.git
```

### 1. configure libsnark
```sh
cd $HOME/zkp-sc

git clone https://github.com/scipr-lab/libsnark.git

cd libsnark

git submodule init && git submodule update

export LIBSNARK_SOURCE_PATH=$HOME/zkp-sc/libsnark
```
### 2. configure ZoKrates
```sh
cd $HOME/zkp-sc

git clone https://github.com/JacobEberhardt/ZoKrates.git
```

### 3. install dependency
```sh
sudo apt-get update 

sudo apt-get install -y \
    build-essential \
    cmake \
    curl \
    libboost-all-dev \
    libgmp3-dev \
    libprocps4-dev \
    libssl-dev \
    pkg-config \
    python-markdown \
    git
```
> Note: Ubuntu 16.04 is libprocps4-dev, and Ubuntu 14.04 is libprocps3-dev

### 4. install cargo and rustc
```sh
curl https://sh.rustup.rs -sSf | \
    sh -s -- --default-toolchain nightly-2018-06-04 -y

source $HOME/.cargo/env
```

### 5. Compile and Build
```sh
cd $HOME/zkp-sc/ZoKrates

cargo build --release
```

## Build with docker
```bash
git clone https://github.com/JacobEberhardt/ZoKrates

cd ZoKrates

cp -f Dockerfile ZoKrates/

docker build -t zokrates .

docker run -ti zokrates /bin/bash

cd ZoKrates/target/release

```

More detail, see README.md in 'ZoKrates'

