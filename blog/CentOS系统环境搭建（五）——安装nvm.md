点击返回[🔗我的博客文章目录](https://percheung.github.io/#/toc)
* 目录
{:toc}
<div onclick="window.scrollTo({top:0,behavior:'smooth'});" style="background-color:white;position:fixed;bottom:20px;right:40px;padding:10px 10px 5px 10px;cursor:pointer;z-index:10;border-radius:13%;box-shadow:0.5px 3px 7px rgba(0,0,0,0.3);"><img src="https://percheung.github.io/blogImg/backTop.png" alt="TOP" style="background-color:white;width:30px;"></div>

# CentOS系统环境搭建（五）——安装nvm

>在我们的日常开发中经常会遇到这种情况：手上有好几个项目，每个项目的需求不同，进而不同项目必须依赖不同版的 NodeJS 运行环境。如果没有一个合适的工具，这个问题将非常棘手。由此[nvm](https://github.com/creationix/nvm)应运而生。nvm是一个node管理工具。使用`nvm` Node版本管理器安装Node.JS。`nvm`允许您在同一台计算机上安装多个Node.JS版本。并且自由切换node版本。

<div style="text-align: center;">
  <img src="https://percheung.github.io/blogImg/nvm-logo-color.png" width="50%" alt="nvm" />
</div>

## 1.安装

安装指令，这个是一键式的，这个如果执行成功可以直接跳到第二步验证。

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.39.1/install.sh | bash
```

若是通过上面这种方式下载不下来，那么只能去官网自己下载压缩包了。

🔗https://github.com/nvm-sh/nvm/releases/tag/v0.39.4

解压

```bash
unzip nvm-0.39.4.zip
```

进入

```bash
cd nvm-0.39.4
```

执行安装

```bash
./install.sh
```

## 2.刷新系统环境

```bash
source ~/.bashrc
```

验证安装

```bash
command -v nvm
```
## 3.查看所有node

```bash
nvm list-remote
```

## 4.安装Node.js版本

```bash
nvm install v16.20.2
```

## 5.查看已安装版本号

```bash
nvm list
```

## 6.使用指定版本

```bash
nvm use v16.20.2
```

## 7.设置默认版本

```bash
nvm alias default v14.21.3
```

## 8.验证

```bash
node -v
```

```bash
npm -v
```

至此，说明node和npm也安装完成，可以正常使用。