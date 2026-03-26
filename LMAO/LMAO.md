# Auto: Language Made for AI OS


大纲:

1. AI
2. OS
3. AI + OS
4. Beyond Single OS


## Intro: AI

> “从群众中来，到群众中去。”

1. Made BY AI
2. Made FOR AI
3. Made of AI

## Intro: OS

1. Language as OS (LaOS)

参考LaOS.jpg

2. 不可能三角

参考Triangle.xlsx

## Progress: Made BY AI

两个月开发：

- 智谱AI的MAX套餐: 100亿Tokens
- 1300+ commits
- 20万行Rust代码
- 1个解释器+6个转译器
- a2c完成90% C语言支持
- a2rs完成80% Rust语言支持
- Auto语言语法95%实现

## Progress: LaOS

1. 内核（语言特性）
    - AutoVM
        - standalone
        - comptime
        - embedded (in MCU)
    - Transpilers:
        - a2rs
        - a2c
        - a2ts
        - a2py
        - a2kt
    - 编译期执行 (CTE)
    - Spec (Trait)
    - OOP (`is`, `has`, `as`)
    - `?T` and `!T`

2. 内存管理
    - 动态内存 vs 静态内存？
        - Default Storage
        - Prelude Config
    - 自动内存回收
        - Linear Type + Borrow Checker
        - AutoFree
        - RC
        - Escape Analysis

3. 异步并发
    - `Task`/`Msg`
    - `~T`

4. 系统调用（标准库）
    - 多后端架构
        - `io.at`
            - `io.vm.at`
            - `io.rs.at`
            - `io.c.at`

5. Shell（ASH）
    - nushell+uutils/coreutils
    - pipeline with Atom
    - cross boundaries
        - MCU <-> Windows
    - smart commands
    - (future) extends to SafeClaw

6. UI（Aura）
    - Aura: AutoUI 
    - targets:
        - WEB: vue (vue3 + shadcn-vue)
        - Desktop:
            - tauri
            - rust (iced/gpui backend)
        - Mobile:
            - jetpack compose
            - ArkTS (Harmony Next)
    - flexiable backend implementations:
        - for WEB, generate Rust backend with HTTP Server
        - for Desktop/VSCode, Rust backend with IPC call
        - (future) for MCU, C backend with LVGL

7. OS Adapters
    - Windows/Linux: Rust
    - SOC: Rust/C++(ROS)
    - MCU: C(FreeRTOS)
    - Mobile/WEB: a2vue, a2jet, a2ark
    - COM: RPC via Auto Virtual Bus

8. DevOp & Distribution
    - AutoMan: universal project manager (builder and package)
    - AutoIDE: Assemble them all

## AI: Made FOR AI


- 专为AI生成设计的语法
- 编译器针对人和AI输出不同错误信息(miette vs JSON)
- Contract Programming via Annotation
- Intention Annotation
- Sample code for AI
- Reverse translation to generate mass codebase for AI
- An Auto skill for generating Auto Code in Claude

## AI: Made FOR AI (cont.)

- Generate Once, Use Everywhere!
    - saves 80%~90% of tokens

- Code for AI, Summary for Human

## AI: Made OF AI

方向一：Auto自制Agent架构

- a2py -> AutoAgent
- SmartCmd -> AutoTool
- AutoDown -> AutoSkill
- AutoDown -> AutoKnowledge

上面四个组件组合成AI Agent集群（SafeClaw）


## AI: Made OF AI

方向二：AI编译加速

- Interact with AI Lang:
    - Triton
    - Mojo
- Direct transpilation:
    - CUDA
    - CANN
    - ROCm
    - MUSA

## AI + OS

- Agent OS

- Cursor -> Claude -> OpenClaw -> Agent OS

- OpenClaw
    - OpenFang
    - 三省六部制

- Agent OS
    - 应该采取什么样的架构？

- SafeClaw
    - transpiled from NanoClaw
    - add features from IronClaw
    - UI with AURA

## Beyond Single OS

1. 汽车行业：“整车开发”
2. 机器人行业：“ROS++”
3. 应用行业：“全栈开发”


------

New PAGES

------

## 整车开发架构图

左侧：全Auto语言

- 主机模块
- 域控节点
- 多个控制器或传感器

三层之间和层内节点间都是通过“AutoMsg”通讯

右侧：整车EE架构

- 中央HPC
- 4个域控ZCU
- 各种MCU

中央HPC和域控ZCU之间通过ETH通讯
MCU和域控之间通过CAN/LIN/ETH通讯

连接线：

1. 左侧的“主机模块”生成Kotlin代码，连接到右侧的“中央HPC”
2. 左侧的域控节点生成C++代码，连接到右侧的“域控ZCU”
3. 左侧的控制器或传感器，生成AutoSAR的C代码，连接到右侧的各种MCU

------

## AutoOS

1. 跨平台虚拟OS (Win/Linux/Mac/Android/Harmony/MCU)
2. Agentic Apps（统一应用商店，统一通讯架构）
3. 开发到部署全流程支持（AutoIDE，AutoUI，AutoMan）
4. OpenSource/OpenBusiness


-------


## Simpler Rust, Better C

- Simpler Rust
    - Script mode with AutoVM interpreter
    - Simpler Lifetime
    - Simpler Generics
    - Simpler Meta programming (like Zig)

- Better C:
    - C + OOP
    - Module system
    - Generics and CTE
    - Safty

