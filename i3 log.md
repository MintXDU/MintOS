polybar上面的应用图标原来是由一个叫 tray 的东西显示的。

> 修改改变窗口的 dpi: 


  1.  修改 ~/.Xresources 文件中的 Xft.dpi
      eg: Xft.dpi: 120
  2.  执行命令: xrdb ~/.Xresources
> Polybar:


1. 安装 Polybar
```
sudo pacman -S polybar
```
2. 配置 Polybar 初始启动, 根据[ polybar 官方指南](https://github.com/polybar/polybar/wiki)
