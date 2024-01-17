---
title: "Hello World!"
weight: 102
---
## 国际惯例
创建源文件main.rs
``` rust
fn main() {
    println!("Hello, world!");
}
```
## 编译main.rs
``` bash
rustc main.rs
```
{{< hint info >}}
rustc是rust的编译器，执行上述命令后会产生一个二进制可执行文件 main
{{< /hint >}}



## 运行
``` bash
./main
```
{{< hint info >}}
如无异常，你应该可以看到输出 Hello, world!

恭喜你:tada::tada:，你已经是一名合格的Rustacean了！
{{< /hint >}}



## 代码分析
{{< hint info >}}
**fn** 是Rust世界的关键字，使用fn关键字来声明一个函数(function)

**main** 是Rust世界的函数入口，任何一个Rust可执行程序都会从main函数开始执行

**函数体** 是使用大括号{}来进行包裹的

**println!** 是宏(macro)，Rust世界中的宏都会以感叹号!结尾，可以从语义上很直观的看出来哪些是函数哪些是宏，println!宏的功能很简单把参数中的字符串输出到屏幕上
{{< /hint >}}

## 扩展思考
{{< hint info >}}
**刚刚编译出来的可执行文件main能否在未安装Rust的计算上直接执行？**  
答案是可以的。Rust源代码文件经过编译器编译和链接后生成的是机器码(Machine Code)
{{< /hint >}}
{{< mermaid >}}
flowchart LR
    Rust源代码 --> Rustc --编译和链接--> 机器码 --> CPU执行
{{< /mermaid >}}
