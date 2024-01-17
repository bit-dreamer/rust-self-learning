---
title: "Hello Cargo!"
weight: 103
---
## 什么是Cargo
在Hello World实验中我们使用了Rustc来进行源代码编译,由于我们的项目规模较小、项目中也没有依赖其他的软件包，因此在教学阶段使用Rustc是一个快速入门的选择。

Cargo是一个Rust构建工具，包含了项目创建、项目构建打包、依赖关系管理等一系列构建管理功能，帮助我们更快更方便的来构建项目。

## 使用Cargo创建Rust项目
``` bash
cargo new hello-world
```
``` bash
.
├── Cargo.toml
├── .git
│   ├── config
│   ├── description
│   ├── HEAD
│   ├── hooks
│   ├── info
│   ├── objects
│   └── refs
├── .gitignore
└── src
    └── main.rs
```
{{< hint info >}}
Cargo.toml 是Cargo项目的配置文件，必须遵循[TOML](https://toml.io/)格式

.git 是Cargo帮助我们创建的Git仓库

.gitignore 用于告诉Git哪些文件或目录应该从版本控制中忽略

src/main.rs 是Cargo项目运行的入口点
{{< /hint >}}

## 使用Cargo构建Rust项目
``` bash
cd hello-world
cargo build
```
``` bash
.
├── Cargo.lock
├── Cargo.toml
├── .git
├── .gitignore
├── src
│   └── main.rs
└── target
    ├── CACHEDIR.TAG
    ├── debug
    │   ├── build
    │   ├── .cargo-lock
    │   ├── deps
    │   ├── examples
    │   ├── .fingerprint
    │   ├── hello-world
    │   ├── hello-world.d
    │   └── incremental
    └── .rustc_info.json
```
{{< hint info >}}
执行完cargo build后，我们注意到多了一些文件，我们目前只需要关心 **target** 目录即可。

在 **target** 目录下有个 **debug** 文件夹，这说明目前我们使用 **cargo build** 命令构建出来的是带有调试信息的debug版本的软件，不能在生产环境中直接使用该版本。

如果我们希望构建出生产环境可用的软件版本，我们应该使用 **cargo build -\-release** 命令来构建
{{< /hint >}}

## 使用Cargo运行Rust项目
``` bash
cd hello-world
cargo run
```
{{< hint info >}}
通过上面的构建命令，我们可以在 **target/debug/hello-world** 找到我们的二进制可执行文件，我们可以在终端中直接执行 **target/debug/hello-world** 来运行程序

cargo run 的作用是把 **cargo build** 和 **target/debug/hello-world** 这两步操作变为一条命令，简化了我们的工作路径


:loudspeaker: 注意

cargo run 执行的是debug版本

cargo run -\-release 执行的是release版本
{{< /hint >}}

## 使用Cargo检查Rust项目
``` bash
cd hello-world
cargo check
```
{{< hint info >}}
你可能会问在什么情况下需要cargo check？

虽然cargo build也会做检查但同时会生成可执行文件，而cargo check只做语法检查速度要比cargo build快的多

因此我们可以在写完一段代码后快速执行一下cargo check来检查我们的代码是否存在问题

或者在某些IDE工具中可以设置 保存代码文件时自动调用cargo check
{{< /hint >}}

:tada: 好了，现在你已经会使用cargo的基本功能了，快进入下一章跟我一起学习rust的其他概念吧。