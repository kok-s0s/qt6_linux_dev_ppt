---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: Prism
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss
---

# Qt Linux Dev

---

# Linux 选择

主要还是看个人喜好

优先推荐 Ubuntu ，可在官网上下载[镜像](https://cn.ubuntu.com/download/desktop)，并制作相对应的 U 盘。

Ubuntu 有相应的[安装教程](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)，可以按照教程一步步执行。

同时 Ubuntu 官网有些不错的文章，在此推荐下

- [**The Linux command line for beginners**](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview)
- [**Ubuntu packages**](https://ubuntu.com/about/packages)

<br>

在 Ubuntu 上遇到困难，建议不仅可以通过搜索来解决，也可以看看 Ubuntu 提供的[开发者文档](https://ubuntu.com/#developer)

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# Ubuntu Dev

开发 C++ 所需

安装完 Ubuntu 之后，建议（按顺序）执行以下命令

```bash
sudo apt-get update
sudo apt-get upgrade

sudo apt-get install vim
sudo apt-get install gcc
sudo apt-get install g++
sudo apt-get install clang-format
sudo apt-get install cmake
sudo apt-get install git
sudo apt-get install python3
```

再去 VSCode [官网](https://code.visualstudio.com/)下载对应的 `deb` 包

打开终端执行安装指令

```bash
sudo dpkg -i code_*_amd64.deb
```

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


---

# VSCode Extension

事半功倍

- `C/C++`
- `clang-Format`
- `CMake`
- `CMake Tools`
- `Git Graph`
- `Markdown Preview Github Styling`
- `Project Manager`
- `Qt tools`
- `Trailing Spaces`

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# Qt

图形化应用开发

推荐在[清华镜像源](https://mirrors.tuna.tsinghua.edu.cn/qt/)里下载需要的 Qt 版本。

可以下载源码后自己编译，这边选择使用 [Qt 在线下载安装器](https://mirrors.tuna.tsinghua.edu.cn/qt/official_releases/online_installers/)，下载 `*.run` 文件。

通过执行以下指令来进行安装

eg: 安装文件为 `qt-unified-linux-x64-online.run`

```bash
# 给执行文件加上读写权限
sudo chmod 777 qt-unified-linux-x64-online.run

./qt-unified-linux-x64-online.run
```

之后会弹出安装指示面板，需要有一个 Qt 的账户（没有可注册）

都按照默认配置即可，注意选择为个人开发所用

安装文件建议放在用户的根目录处 eg `/home/USER/QtVERSION`

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# Qt

图形化应用开发

Qt 安装完仍需要配置变量后才可正常使用

eg

在 Ubuntu 22.04 中配置变量的操作

```bash
vim /etc/bash.bashrc
```

在 `bash.bashrc` `文件中加入（一般在最后）以下语句

```bash
# Qt6.4.1
# VERSION = 6.4.1
export PATH="/home/USER/QtVERSION/Tools/QtCreator/bin:$PATH"
export PATH="/home/USER/QtVERSION/6.4.1/gcc_64:$PATH"
```

可以在终端下输入 `qtcreator`，看看 QtCreator 是否会被启动。

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: two-cols
---

# VSCode_Qt_CMake

一套组合

打开 VSCode，按下快捷键 Ctrl + Shift + P，输入 `CMake: Quick Start`，创建一个应用程序。

编写 CMakeLists.txt, 内容参考如右边所示。

<br>

更多有关 Qt 开发下 CMake 编写的规则可以看 [QT 的官方文档](https://doc.qt.io/qt-6/cmake-get-started.html#building-a-c-gui-application)学习，也可以看 CMake 的[文档](https://cmake.org/cmake/help/latest/)了解更多。

::right::

### CMakeLists.txt

```cpp
cmake_minimum_required(VERSION 3.16)

project(helloworld VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS Widgets)
qt_standard_project_setup()

add_executable(helloworld
    mainwindow.ui
    mainwindow.cpp
    main.cpp
)

target_link_libraries(helloworld PRIVATE Qt6::Widgets)

set_target_properties(helloworld PROPERTIES
    WIN32_EXECUTABLE ON
    MACOSX_BUNDLE ON
)
```

<style>
h1, h3{
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# 禁用 Wayland

确保 Qt 的有些 API 能够正常使用 eg -- `QCursor:;setPos()`

参考文章 - [How to enable/disable wayland on Ubuntu 22.04 Desktop](https://linuxconfig.org/how-to-enable-disable-wayland-on-ubuntu-22-04-desktop)

```bash
sudo vim /etc/gdm3/custom.conf
```

输入上述指令去编辑 `/etc/gdm3/custom.conf` 配置文件

将 `WaylandEnable` 设置为 `false`

```bash
WaylandEnable=false
```

然后重启 [gdm](https://baike.baidu.com/item/gdm/4597441)

```bash
sudo systemctl restart gdm3
```

之后再注销用户，再登陆即可。

<style>
h1, h3{
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>
