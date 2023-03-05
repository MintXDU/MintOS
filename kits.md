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

### 7. 安装 nvidia 独显驱动(已有intel核显)(安装前一定要保存快照！！！)
```
sudo pacman -S nvidia nvidia-settings lib32-nvidia-utils
```
参考文档：
[NVIDIA - archwiki](https://wiki.archlinuxcn.org/wiki/NVIDIA)
[安装N卡驱动](https://wynio.online/posts/37c1/)
[GRUB 如何设置 Linux 内核参数](https://razonyang.com/zh-hans/blog/linux/grub/kernel-parameters/)
主要参考 wiki
其中：
1. **在引导加载程序中设置内核参数 ibt=off**是必须的。具体操作为：将内核参数追加到 /etc/default/grub 文件中的 GRUB_CMDLINE_LINUX_DEFAULT，每个参数以空格隔开。
```
GRUB_CMDLINE_LINUX_DEFAULT="loglevel=3 quiet ibt=off"
```
2.  **把kms 从 /etc/mkinitcpio.conf 里的HOOKS 数组中移除，并重新生成 initramfs。** 也是必须的。
```
mkinitcpio -P
```
