## 通用工具
### 1. 通过命令行进行网络连接管理:
下载包 networkmanager
```
nmcli --help
```
### 2. 修改 vim 配置
修改文件 /etc/vimrc

### 3. 加工图片工具: ```imagemagick```
单单修改图片的后缀名称有时候是不能实质性地更改图片的属性的。\
可以使用命令
```
convert name.jpg name.png
```
把 jpg 图片转换成 png 图片。\
更多命令请通过 man 查阅。

### 4. 安装配置文件管理工具 ```chezmoi```
```
sudo pacman -S chezmoi
```
具体操作，查看[官方文档](https://www.chezmoi.io/quick-start/)。

### 5. 安装 github-cli , github 命令行工具
```
sudo pacman -S github-cli
```

### 6. 配置 tex 编辑环境
```
sudo pamcan -S texlive-most # 安装很多关于 tex live 的包
sudo pamcan -S texlive-core # 安装核心
sudo pamcan -S texlive-langchinese # 安装中文支持
```
参考文档：

[在 archlinux 上搭建 latex 环境并使用 vscode 编写](https://huangno1.github.io/arhlinux_vscode_latex_install_configuration/)

[Tex Live(简体中文) archwiki](https://wiki.archlinux.org/title/TeX_Live_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
