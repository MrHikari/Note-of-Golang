# Note-of-Golang
 This note is my note of Golang.

# Go语言入门
===

## Go的安装
---
安装之前需要了解几个必要的文件目录：

- **GOROOT** 目录，该目录为解压压缩包所存放的目录。Mac我使用[home brew](http://brew.sh/)安装方便快捷安装Go，如果你想要在你的 Mac 系统上安装 Go，则必须使用 `Intel 64` 位处理器，Go 不支持 `PowerPC` 处理器。默认在/usr/local/Cellar/go/版本/libexec，**Homebrew**有编译过程，安装需要时间。

```bash
brew update && brew upgrade # 更新 Homebrew 的信息
brew install go             # 安装 go
brew upgrade go             # 更新 go
brew update go              # 单独更新 golang
```

- 新建 **GOPATH** 目录，即为我们的“工作目录”，该目录可以有多个，建议只设置一个。
- GOPATH 目录下新建 `src` 目录，该目录用于存放第三方库源码，以及存放项目的源码。
- GOPATH 目录下新建 `bin` 目录，该目录用于存放项目中所生成的可执行文件。
- GOPATH 目录下新建 `pkg` 目录，该目录用于存放编译生成的库文件。

## Mac下Go语言开发环境设置
---
**分开bash和zsh**
```
vim ~/.bash_profile
# 加入
export GOPATH=$HOME/go
export PATH=$HOME/bin:$GOPATH/bin:$PATH
# 保存
source ~/.bash_profile
```
如果你用的是默认的终端这样做就可以了，但是我的Mac中除了bash还有zsh，平时是用zsh的，所以为了bash和zsh都可以运行go需要这样配置

```
vim ~/.profile
# 加入
export GOPATH=$HOME/go
export PATH=$HOME/bin:$GOPATH/bin:$PATH
# 保存
```
```
vim ~/.bash_profile
# 加入
source ~/.profile
保存
```
```
vim ~/.zshrc
# 加入
source ~/.profile
# 保存
```
这样两个终端的环境变量就都配置完成了。