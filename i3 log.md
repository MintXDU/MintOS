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

3. tray相关配置:
- tray-position = right/..

4. fontawesome 字体?

5. 设置壁纸
安装 feh
```
sudo pacman -S feh
```
在 i3 配置文件中加入
```
exec_always --no-startup-id feh --bg-scale PathToPicture
```
更多 feh 操作 请查看[ feh archwiki](https://wiki.archlinux.org/title/Feh_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
