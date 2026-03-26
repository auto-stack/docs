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

## AI: Made of AI

- Generate Once, Use Everywhere!
    - saves 80%~90% of tokens

- Code for AI, Summary for Human

## AI + OS

- Agent OS

- Cursor -> Claude -> OpenClaw -> Agent OS

- OpenClaw
    - OpenFang
    - 三省六部制

- SafeClaw
    - transpiled from NanoClaw
    - add features from IronClaw
    - UI with AURA

## Beyond Single OS

1. 汽车行业：“整车开发”
2. 机器人行业：“ROS++”
3. 应用行业：“全栈开发”
