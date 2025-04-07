## 开场

三个话题

- OS
- Auto语言
- 车载嵌入式开发

## 引子

1. 我们是做什么的？

车载嵌入式开发：

- 全景图（五大域）
- 点亮地图

2. 理想 vs 现实

理想

One Ring to Rule them All

视角

- 程序员：One Codebase to rule them all
- 操作系统：One OS to rule them all
- 语言开发者：One Lang to rule them all

现实

- App
- OS
- Lang

Auto的由来：弥补现实和理想的差距


## 车用MCU


理想：C to Rule them All?

现实：C ruled by them all

- 芯片
- SDK
- 配置
- 编译器
- IDE
- 调试设备
- 网络协议

画图：1 to N1*N2*N3

视角：

- 软件供应商（我们）
- 车厂
- 硬件供应商
- 中间商

问题总结：

- 生态碎片化
- 复用率低
- 配置繁琐

花了很多精力，加了很多班，身体被掏空，但是感觉没做多少东西。

## 问题解决

## 碎片化？

### 1. HAL

类比：OS的HAL

### 2. MCAL

类比：OS的Driver

### 3. 配置工具

类比：OS的配置文件体系

### 4. 编译器、IDE、调试设备

类比：OS的编译器体系

### 5. UI

类比：OS的UI

### 6. 中间商胜出

引用福特CEO的视频

小结：配置文件+UI+代码生成+C

- 尝试学习OS的解决方案，但是没有那么好的条件
- 一切资料都要转化为C语言代码
- 想要做OS，最终做成了拙略的“many to C”编译器

## 复用率？

解决方案：模块化

OS解决方案：微内核、操作系统模块化

## 配置繁琐？

解决方案：

- Code first：配置语言（如Vector的XML->DML、阿里的YAML->KCL）
- UI：配置文件+UI同步更新

OS解决方案：配置文件+UI同步更新
- 配置文件：ini、json、xml、yaml、toml
- 交互功能：shell、UI
- 动态配置：脚本

OS是怎么解决的？

OS方案的局限性：

- MCU资源受限：
  - 配置文件的方案不可用
  - 交互功能缺失
  - 脚本功能不可用

回归到本质：在MCU中，一切信息最终都要落地到C语言。

最终解决方案：OS+Compiler

- 碎片化：Automan+Autogen
- 复用率：语言模块化、标准库模块化、三方库模块化
- 配置：Atom+AutoConfig+AutoScript
- 交互：AutoShell+AutoUI

Auto语言的出发点恰好在两个极端：

- 配置语言：JSON -> Atom -> AutoConfig -> AutoScript
- 静态语言：C -> 面向对象 -> 模块化 -> 泛型/编译器执行 -> AutoLang

最后，从这两个端点触发，融合起来，形成了Auto语言的雏形。


## 语言的不可能三角

- 运行性能
- 开发效率
- 安全


C自己可以解决吗？

- 配置文件
- 模块化
- 测试框架

Rust/Zig可以解决吗？

- 配置文件

Python等动态语言可以解决吗？

- 静态效率

综合：

1. 一门语言，解决不了问题
2. 静态语言+动态语言+配置文件结合
3. 考虑MCU的生态限制，动态语言必须最终编译为静态语言

## 解决方案

Lang as OS！

- 静态语言：C/Rust
- 动态语言：Auto
- 配置文件：AutoConfig
- 交互功能：AutoShell/AutoUI
- 模块化：Automan
- 微内核：语言特性微内核、标准库微内核

AutoLang并不是一门语言，而是统一风格的Auto语言家族。

- Atom：静态数据表达 vs JSON/XML
- AutoScript：动态脚本 vs Python/JS
- AutoLang：类Rust的静态语言

