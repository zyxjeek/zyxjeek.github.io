---
title: Linux配置oh-my-zsh的步骤
date: 2022-11-20 11:10:46
tags: Linux
---

## 1. 安装zsh，oh-my-zsh

- 首先安装zsh：`sudo apt install zsh`

- 然后安装oh-my-zsh：`sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"`

## 2. 安装插件

- 安装高亮插件：

  ```bash
  cd ~/.oh-my-zsh/custom/plugins/
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
  ```

- 安装主题插件：`git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`

- 将设置应用到.zshrc：

  ```bash
  ### ................ ###
  ZSH_THEME="powerlevel10k/powerlevel10k"
  ### ................ ###
  plugins = (git sudo zsh-syntax-highlighting)
  ### ................ ###
  source ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
  ```

  
