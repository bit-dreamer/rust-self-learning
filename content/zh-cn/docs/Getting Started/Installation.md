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
#需要注销用户或者重启计算机之后再执行安装脚本
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
#安装后查看版本
rustc --version
cargo --version
```
{{< hint info >}}
**为什么不直接按照官方的命令安装？**  
默认的官方命令会连接国外的服务器进行rust安装包下载速度较慢，因此我们可以通过设置国内的镜像服务器来提高下载Rust的速度。
{{< /hint >}}



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

{{< hint info >}}
**为什么要加速？**  
crates.io的服务器在国外下载速度较慢，因此我们可以通过设置国内的镜像服务器来提高下载crates的速度。
{{< /hint >}}



## 如何更新Rust
``` bash
rustup update
```



## 如何卸载Rust
``` bash
rustup self uninstall
```