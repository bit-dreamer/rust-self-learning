---
title: "环境准备"
weight: 101
---
## 环境准备
- 操作系统 [Ubuntu Desktop](https://ubuntu.com/desktop/)
- Debugger 
    - [LLDB](https://lldb.llvm.org/)(**推荐**)
    - [GDB](https://sourceware.org/gdb/)
- 编辑器 [VSCode](https://code.visualstudio.com/) 并安装插件 [rust-analyzer](https://code.visualstudio.com/docs/languages/rust)
- 开源镜像站 
    - [清华大学镜像站](https://mirrors.tuna.tsinghua.edu.cn/) 
    - [中国科技大学镜像站](https://mirrors.tuna.tsinghua.edu.cn/)

## Rust安装
``` bash
echo 'export RUSTUP_DIST_SERVER=https://mirrors.ustc.edu.cn/rust-static' >> ~/.bash_profile
echo 'export RUSTUP_UPDATE_ROOT=https://mirrors.ustc.edu.cn/rust-static/rustup' >> ~/.bash_profile
sudo reboot 0
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
## crates.io 镜像加速
``` bash
mkdir -vp ${CARGO_HOME:-$HOME/.cargo}

cat << EOF | tee -a ${CARGO_HOME:-$HOME/.cargo}/config
[source.crates-io]
replace-with = 'mirror'

[source.mirror]
registry = "sparse+https://mirrors.tuna.tsinghua.edu.cn/crates.io-index/"
EOF
```