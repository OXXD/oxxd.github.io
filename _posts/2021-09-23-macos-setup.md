---
layout: post
title: 给 Web 开发者看的 macOs 新机设置指南
description: ""
modified: 2021-09-23
tags: [post frontend]
comments: true
share: true
---

以下内容假使读者已具备正确上网技能，如果不能正确上网部分链接会无法打开。

## 1. 安装 Homebrew

`Homebrew` 是包管理工具，也可安装管理 `GUI` 软件，第一件事就是打开 `term.app` 安装 `Homebrew`，安装命令直接复制自[官网](https://brew.sh)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2. 通过 Homebrew 安装 iTerm2

`iTerm2` 相比自带的终端拥有更多功能以及更好用的分屏

```bash
brew install iterm2
```

### 2.1 配置 iTerm2

配置支持 ⌘ ← , ⌘ →, ⌥ ←, ⌥ → 快捷键在终端中快速调整单词

<figure class="half">
    <a href="https://i.stack.imgur.com/NLIVi.gif">
        <img src="https://i.stack.imgur.com/NLIVi.gif" alt="">
    </a>
	<figcaption><span>快捷键</span>.</figcaption>
</figure>


## 3. 安装 Oh My Zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## 4. 配置 .zshrc

### 4.1 增加 zsh 插件

编辑 `~/.zshrc`

```bash
vi ~/.zshrc
```

修改 plugins 部分增加插件 `z`, `zsh-autosuggestions`, `zsh-syntax-highlighting`

```bash
plugins=(git z zsh-autosuggestions zsh-syntax-highlighting)
```

其中 `zsh-autosuggestions`, `zsh-syntax-highlighting` 需要用以下命令下载

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### 4.2 去除用户名显示

编辑 `~/.zshrc`

```bash
vi ~/.zshrc
```

加入以下内容

```bash
# User configuration
export DEFAULT_USER="$(whoami)"
```

### 4.3 增加快捷命令

编辑 `~/.zshrc`

```bash
vi ~/.zshrc
```

加入以下内容

```bash
alias proxy='export https_proxy=http://127.0.0.1:8888;export http_proxy=http://127.0.0.1:8888;export all_proxy=socks5://127.0.0.1:8889'
alias unproxy='unset https_proxy http_proxy all_proxy'
```

### 4.4 安装 Powerline 字体

如果额外设置了主题带有特殊字体可能需要再安装 Powerline 字体

```
cd ~/Developer

git clone https://github.com/powerline/fonts.git  # 将 Powerline 字体文件下载到「下载」文件夹中

cd fonts && ./install.sh  # 安装所有 Powerline 字体

```

安装好之后按 ⌘, 打开终端偏好设置，在描述文件 > 文本中更改字体。

## 5. 安装 nvm 和 Node.js

通过 `nvm` 安装 `Node.js` 可以方便的进行版本切换

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

```bash
nvm install --lts
nvm use node
```

## 6. 安装一些 Node.js 全局依赖

```bash
npm i -g serve @vue/cli
```

## 7. 使用 Homebrew 安装需要的软件

这部分大家可以自己选择安装，安装自己需要的软件即可

```bash
brew install nginx thefuck
```

```bash
brew install alfred sizeup caffeine google-chrome notion teamviewer charles obs visual-studio-code firefox istat-menus postman vlc gas-mask macdown spotify cheatsheet
```

## Reference

- [Homebrew](https://brew.sh)
- [iTerm2](https://iterm2.com)
- [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh)
- [让你的 Mac 提前用上 macOS Catalina 的 Shell —— Oh My Zsh 配置指南](https://blog.hly0928.com/post/set-up-oh-my-zsh-on-macos/)
- [How to set keyboard shortcuts to jump to beginning/end of line?](https://stackoverflow.com/questions/6205157/how-to-set-keyboard-shortcuts-to-jump-to-beginning-end-of-line)
- [nvm](https://github.com/nvm-sh/nvm)
- [Blog Series: Setting up a new OS X development machine](https://mattstauffer.com/blog/series/setting-up-a-new-os-x-development-machine/)
- [My wonderful world of macOS](https://github.com/nikitavoloboev/my-mac-os)