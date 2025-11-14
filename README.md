# mytexmk 工具

一个简化 LaTeX 文档编译和模板管理的工具。

## 功能特性

1. 编译 XeLaTeX 文档
2. 清理编译产生的辅助文件
3. 基于模板快速创建新项目

## 安装

```bash
# 添加执行权限
chmod +x ~/apps/tex_onceMake/scripts/mytexmk

# 创建软链接以便全局使用（推荐）
sudo ln -s ~/apps/tex_onceMake/scripts/mytexmk /usr/local/bin/mytexmk

# 或者添加到 PATH 环境变量
echo 'export PATH="$HOME/apps/tex_onceMake/scripts:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

## 使用方法

### 1. 编译文档

```bash
# 编译指定的 tex 文件
mytexmk main.tex

# 自动查找当前目录下的唯一 tex 文件并编译
mytexmk
```

编译过程会执行以下操作：
1. 使用 `latexmk -xelatex` 编译文档
2. 使用 `latexmk -c` 清理辅助文件

### 2. 使用模板创建新项目

```bash
# 基于模板创建新项目（新语法）
mytexmk <模板名称> <项目名称>
```

例如：
```bash
# 基于"计算机学报"模板创建名为"myPaper"的项目
mytexmk 计算机学报 myPaper
```

### 3. 查看可用模板

模板存放在 `template/` 目录下，每个子目录都是一个可用的模板。

## 依赖

- TeXLive 发行版（包含 xelatex 和 latexmk）

```bash
# Ubuntu/Debian 系统安装命令
sudo apt install texlive-latex-extra latexmk
```

## 许可证

MIT License


## 致谢
git@github.com:dufe-fintech/Chinese-Journal-of-Computers.git