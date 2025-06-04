## AutoStack相关文档

这个仓库收录AutoStack相关的文档。

### AutoStack简介

Soutek AutoStack是索维软件研发的一系列开发工具，主打自动化功能。

Auto这个名字有双重含义：
- *Automobile*：汽车
- *Automation*：自动化

因此AutoStack的寓意是“把自动化带到汽车行业”，即"Automation for Automobiles"。

AutoStack现有如下工具链：
- [AutoLang](https://gitee.com/auto-stack/auto-lang)：Auto语言，索维软件自主研发的编程语言，包括三个变种
  - AutoConfig，类JSON/XML的配置语言
  - AutoScript，动态脚本语言
  - AutoTemplate，模板语言，用于生成代码
- [AutoMan](https://gitee.com/auto-stack/auto-man)：Automan工具是Auto语言和C语言的编译工具和依赖包管理器。
- [AutoUI](https://gitee.com/auto-stack/auto-ui)：基于Auto和Rust实现的UI库，当前主要用来制作配置工具界面
- [AutoRTOS](https://codeup.aliyun.com/soutek/os)：基于FreeRTOS，适配MCU的嵌入式实时操作系统


未来规划的工具：
- AutoGen：基于AutoTemplate的代码生成工具。主要用来生成C语言配置代码。
- AutoShell：跨平台的Shell环境，语法为AutoScript。
- AutoNet：网络协议栈适配工具，当前支持CAN/LIN，未来扩展到ETH、FlexRay等网络。
- AutoDocs：文档生成工具，从代码自动生成相关文档。
- AutoIDE：集成了上述所有工具的综合开发环境，基于Zed实现。

### Rust学习资料

Rust语言的学习资料：

- [Rust](./Rust/README.md)

编译器相关的学习资料：

- [Compiler](./Compiler/README.md)

UI库相关的学习资料：

- [UI](./UI/README.md)


### LaOS: Language As OS

- [LaOS](./LaOS/slides.md)


