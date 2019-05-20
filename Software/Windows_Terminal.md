Windows Terminal
[微软最爽命令行工具发布！引诱开发者叛逃Mac，开源六小时冲上GitHub第二](https://mp.weixin.qq.com/s/YYzvi4FXwwCK7Hk-TwZ8kA)


##  什么是Windows Terminal
Windows Terminal是微软推出的新的命令行应用程序，提供多标签、分割窗口、快捷键、完整的Unicode字符支持等功能。

最重要的是，它支持PowerShell，Cmd，WSL（Windows的Linux子系统）和SSH等命令行程序，可以说是全平台制霸，简化开发者的工作流程。

什么Cygwin、MinGW、PuTTY，统统可以丢掉！

而且，颜值即正义！微软还给Windows Terminal加入很多细节功能，让它更美观。


除了这个新的命令行工具之外，微软还发布了完整内核的Linux子系统WSL 2。

当真是直击开发者G点。

长期以来，Linux和Mac下的命令行工具自成一派，Windows却是另一套命令系统。

这也是很多开发者不选择Windows系统的原因。

今后还买什么Mac，还装什么Linux系统？

Windows电脑也能和前两者一样轻松做开发了。

## 现在就能上手
如果你已经迫不及待地想要试试Terminal，可以通过下面的GitHub链接，下载、构建和运行这一命令行工具。

```html
https://github.com/microsoft/Terminal
```

需要注意的是，这个项目使用git子模块处理一些依赖项，想要确保子模块更新，请在构建器使用如下命令检查：
```
git submodule update --init --recursive
```
其中，OpenConsole.sln可在Visual Studio中构建，或者使用MSBuild通过命令行来构建：

```
nuget restore OpenConsole.sln
msbuild OpenConsole.sln
```
在/tools文件中，还有一组脚本，能够用于自动化构建和运行测试的过程。

截止到现在， 这一项目已经在GitHub上斩获了4200+标星。微软正式宣布之后，6小时就冲上了GitHub趋势榜第二的位置。


