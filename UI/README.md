## UI库入门资料



### Rust常见UI库

- [gpui](https://www.gpui.rs/) - 这个是AutoUI的底层库，基于WebGPU实现的跨平台UI库。
- [iced](https://iced.rs/) - 基于ELM架构实现的UI库，特点是简单易用。未来也会作为AutoUI的后端之一。
- [egui](https://github.com/emilk/egui) - 类似imgui的立即模式UI库，小巧却强大。


### Auto UI

AutoUI库暂时的选型如下：

1. 底层UI渲染基于gpui
2. 控件库采用[gpui-component](https://github.com/longbridgeapp/gpui-component)

考虑用gpui的原因主要是它是[Zed](https://zed.dev/)IDE的底层库，算是Rust圈中唯一实现了可商用的IDE的UI库。
未来AutoIDE考虑基于Zed来实现。
