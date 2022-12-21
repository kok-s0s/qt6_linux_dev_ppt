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

在 Ubuntu 上遇到困难，建议不仅可以通过搜索来解决，也可以看看 Ubuntu 提供的[开发者信息](https://ubuntu.com/#developer)

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
