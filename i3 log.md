### 双系统挂载 windows 盘
  推荐博客：[Linux下通过修改fstab来自动挂载Windows 分区](https://cloud.tencent.com/developer/article/1559411)


### 修改改变窗口的 dpi: 


  1.  修改 ~/.Xresources 文件中的 Xft.dpi
      eg: Xft.dpi: 120
  2.  执行命令: xrdb ~/.Xresources
<br>

### Polybar


1. 安装 Polybar
```
sudo pacman -S polybar
```
2. 配置 Polybar 初始启动, 根据[ polybar 官方指南](https://github.com/polybar/polybar/wiki)

3. tray相关配置:
- tray-position = right/..

4. fontawesome 字体?

<br>

### 设置壁纸
安装 feh
```
sudo pacman -S feh
```
在 i3 配置文件中加入
```
exec_always --no-startup-id feh --bg-scale PathToPicture
```
更多 feh 操作 请查看[ feh archwiki](https://wiki.archlinux.org/title/Feh_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))

<br>

### 控制音量麦克风输入输出设备

1. 安装 pacmixer
```
yay -S pacmixer
```
$\qquad$通过可视化命令行来控制

2. 安装 pa-applet-git
```
yay -S pa-applet-git
```
命令行输入```pa-applet```在托盘中启动可视化管理音频工具。

<br>

### rofi 相关

1. 安装rofi
```
sudo pacman -S rofi
```

2. 通过 rofi 使用剪切板
    - ```yay -S rofi-greenclip```
    - 根据官方文档，更新```~/.config/greenclip.toml```文件
    - 在 i3 中添加快捷键```bindsym $mod+c exec --no-startup-id rofi -modi "clipboard:greenclip print" -show clipboard -run-command '{cmd}'```
3. 通过 rofi 配置网络
    - ```yay -S networkmanager-dmenu-git```
    - 在 i3 中添加快捷键```bindsym $mod+n exec --no-startup-id networkmanager_dmenu```
4. 通过 rofi 配置蓝牙
    - ```yay -S rofi-bluetooth```
    - 在 i3 中添加快捷键```bindsym $mod+b exec --no-startup-id rofi-bluetooth```

<br>



## 一些错误

### 如果你发现 locale 之后出现异常，比如所有变量值都为 posix <br>

这可能是你用户使用的 sh 的问题(如 zsh)，它可能没有 resource /etc/profile.d/locale/sh . 导致 locale 均为默认值 posix. <br>
有两种方法：
1. 从根本上解决问题: 

$\qquad$ 如果你使用的是 bash 的话，可能没有出现这种问题，因为 bash 会加载 /etc/profile 来获取环境变量，但是 zsh 是使用 /etc/zsh/，按顺序加载其下面的 zshenv, zprofile, zshrc, zlogin 文件.\
$\qquad$ 如果在 /etc/zsh/zprofile 下面相应的环境变量就可以获取正确的环境变量。\
$\qquad$ 对本问题来说，即在 /etc/zsh/zprofile 中加入 source /etc/profile

2. 借助 ssdm:

$\qquad$ 可以在文件 ~/.xprofile 中添加语句
```
resource /etc/profile.d/locale.sh
```
$\qquad$ SSDM 在启动时会先执行 ~/.profile 等文件

### 文件管理器出现无权限挂载等问题

查看[ archwiki 相关文档](https://wiki.archlinux.org/title/PCManFM_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E6%8C%82%E8%BD%BD%E8%AE%BE%E5%A4%87%E6%97%B6%E5%80%99%E6%8F%90%E9%86%92_%22Not_authorized%22)

### flameshot 每次使用都会卡顿一段时间
这是因为每次使用 falmeshot，它都会给出一个通知窗口，如果你的系统没有通知系统，flameshot 就无法寻找到如何通知你，所以卡顿。
安装 dunst 可以解决你的问题。
